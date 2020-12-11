## AZ

These settings apply only when `--az` is specified on the command line.

``` yaml $(az)
az:
  extensions: adds
  package-name: azure-mgmt-domainservices
  namespace: azure.mgmt.domainservices
az-output-folder: $(azure-cli-extension-folder)/src/adds
python-sdk-output-folder: "$(az-output-folder)/azext_adds/vendored_sdks/domainservices"
extension-mode: experimental

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

        - where:
            group: DomainServices
            op: CreateOrUpdate#Create
            param: replicaSets|domainName
          required: true

        - where:
            type: DomainService
            prop: ldapsSettings|resourceForestSettings|domainSecuritySettings|notificationSettings
          flatten: true

        - where:
            param: domainServiceName
          alias:
            - name
            - n

        - where:
            param: domainName
          alias:
            - domain

        - where:
            param: notifyGlobalAdmins
          alias:
            - notify_global_admins

        - where:
            param: notifyDcAdmins
          alias:
            - notify_dc_admins

        - where:
            param: additionalRecipients
          alias:
            - additional_recipients

        - where:
            param: ntlmV1
          alias:
            - ntlm_v1

        - where:
            param: tlsV1
          alias:
            - tls_v1

        - where:
            param: syncNtlmPasswords
          alias:
            - sync_ntlm_passwords

        - where:
            param: syncKerberosPasswords
          alias:
            - sync_kerberos_passwords

        - where:
            param: syncOnPremPasswords
          alias:
            - sync_onprem_passwords

        - where:
            param: ldaps
          alias:
            - ldaps

        - where:
            param: externalAccess
          alias:
            - external_access

        - where:
            param: pfxCertificate
          alias:
            - pfx_cert

        - where:
            param: pfxCertificatePassword
          alias:
            - pfx_cert_password

        - where:
            param: settings
          alias:
            - forest_settings

        - where:
            param: resourceForest
          alias:
            - forest

        - where:
            param: etag
          hidden: true
```