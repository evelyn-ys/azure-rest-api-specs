## AZ

These settings apply only when `--az` is specified on the command line.

``` yaml $(az)
az:
  extensions: ad
  package-name: azure-mgmt-domainservices
  namespace: azure.mgmt.domainservices
az-output-folder: $(azure-cli-extension-folder)/src/ad
python-sdk-output-folder: "$(az-output-folder)/azext_ad/vendored_sdks/domainservices"
extension-mode: stable

directive: 
    - where:
        group: ad domain-service
      set:
        group: ad ds

cli:
    cli-directive:
        - where:
            group: "*"
          hidden: true

        - where:
            group: DomainServices
          hidden: false
          set:
            extensionMode: 'experimental'

        - where:
            param: domainServiceName
          alias:
            - name
            - n

        - where:
            param: etag|location
          hidden: true

        - where:
            group: DomainServices
            op: CreateOrUpdate#Create
            param: replicaSets|domainName
          required: true

        - where:
            group: DomainServices
            op: Update
            param: domainName
          hidden: true

        - where:
            type: DomainService
            prop: ldapsSettings|resourceForestSettings|domainSecuritySettings|notificationSettings
          flatten: true

        - where:
            param: domainName
          alias:
            - domain
```