## CLI

These settings apply only when `--cli` is specified on the command line.

``` yaml $(cli)
cli:
    test-scenario:
      - name: CreateDomainService
      - name: ListDomainServicesByResourceGroup
      - name: ListDomainServicesBySubscription
      - name: UpdateDomainService
      - name: GetDomainService
      - name: DeleteDomainService
```