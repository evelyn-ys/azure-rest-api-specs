## AZ

These settings apply only when `--az` is specified on the command line.

``` yaml $(az)
az:
  extensions: adb2c
  package-name: azure-mgmt-azureadb2c
  namespace: azure.mgmt.azureadb2c
az-output-folder: $(azure-cli-extension-folder)/src/adb2c
python-sdk-output-folder: "$(az-output-folder)/azext_adb2c/vendored_sdks/azureadb2c"
extension-mode: experimental

directive:
  - where:
      group: adb2c b2-c-tenant
    set:
      group: adb2c tenant

cli:
    cli-directive:
      - where:
          group: Operations
        hidden: true
          
```