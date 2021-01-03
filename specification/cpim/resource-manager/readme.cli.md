## CLI

These settings apply only when `--cli` is specified on the command line.

``` yaml $(cli)
cli:
    test-scenario:
      - name: Check name availability - available
      - name: Check name availability - taken
      - name: Create tenant
      - name: B2CTenants_ListByResourceGroup
      - name: B2CTenants_ListBySubscription
      - name: Update tenant
      - name: Get tenant
      - name: Delete tenant
```