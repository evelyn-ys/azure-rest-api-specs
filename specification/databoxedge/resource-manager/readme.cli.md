## CLI

These settings apply only when `--cli` is specified on the command line.

``` yaml $(cli)
cli:
  cli-name: databoxedge
  package-name: azure-mgmt-databoxedge
  namespace: azure.mgmt.databoxedge
  cli-directive:
    - where:
        group: StorageAccountCredentials
        op: CreateOrUpdate.*
      hidden: true
    - where:
        group: StorageAccounts
        op: CreateOrUpdate.*
      hidden: true
  test-scenario:
      general:
        - name: ListSkus
      device_general:
        - name: DataBoxEdgeDevicePut
        - name: DataBoxEdgeDeviceGetByName
        - name: DataBoxEdgeDeviceGetByResourceGroup
        - name: DataBoxEdgeDeviceGetBySubscription
        - name: DataBoxEdgeDevicePatch
        - name: DataBoxEdgeDeviceGetByName
        - name: DataBoxEdgeDeviceDelete
      order:
        - name: OrderPut
        - name: OrderGet
        - name: OrderGetAllInDevice
        - name: OrderDelete
```