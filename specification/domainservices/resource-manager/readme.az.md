## AZ

These settings apply only when `--az` is specified on the command line.

``` yaml $(az)
az:
  extensions: adds
  package-name: azure-mgmt-domainservices
  namespace: azure.mgmt.domainservices
az-output-folder: $(azure-cli-extension-folder)/src/adds
python-sdk-output-folder: "$(az-output-folder)/azext_adds/vendored_sdks/domainservices"

directive: 
    - where:
        group: adds domain-service
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