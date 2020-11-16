## AZ

These settings apply only when `--az` is specified on the command line.

``` yaml $(az)
az:
    extensions: storage
    namespace: azure.mgmt.storage
    package-name: azure-mgmt-storage
az-output-folder: $(azure-cli-extension-folder)/src/storage-preview
python-sdk-output-folder: "$(az-output-folder)/azext_storage_preview/vendored_sdks/azure_mgmt_storage/v2019_06_01"
# add additinal configuration here specific for Azure CLI
# refer to the faq.md for more details
directive:
  - where:
      group: "storage local-user"
    set:
      group: "storage account local-user"

cli:
    cli-directive:
        - where:
            group: "*"
            op: "*"
          hidden: true
        - where:
            group: "LocalUsers"
            op: "*"
          hidden: false
        - where:
            group: "LocalUsers"
          set:
            extensionMode: "preview"
```