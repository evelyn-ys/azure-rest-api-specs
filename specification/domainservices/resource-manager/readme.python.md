## Python

These settings apply only when `--python` is specified on the command line.
Please also specify `--python-sdks-folder=<path to the root directory of your azure-sdk-for-python clone>`.
Use `--python-mode=update` if you already have a setup.py and just want to update the code itself.

``` yaml $(python)
python:
  azure-arm: true
  license-header: MICROSOFT_MIT_NO_VERSION
  payload-flattening-threshold: 2
  namespace: azure.mgmt.domainservices
  package-name: azure-mgmt-domainservices
  title: DomainservicesManagementClient
  description: The DomainServices Client.
  clear-output-folder: true
  no-namespace-folders: true
```

### Python multi-api

Generate all API versions currently shipped for this package

```yaml $(python) && $(multiapi)
batch:
  - tag: package-2020-01
  - tag: package-2017-06
  - tag: package-2017-01
```

### Tag: package-2020-01 and python

These settings apply only when `--tag=package-2020-01 --python` is specified on the command line.
Please also specify `--python-sdks-folder=<path to the root directory of your azure-sdk-for-python clone>`.

``` yaml $(tag) == 'package-2020-01' && $(python)
python:
  namespace: azure.mgmt.domainservice.v2020_01_01
  output-folder: $(python-sdks-folder)/domainservices/azure-mgmt-domainservices/azure/mgmt/domainservices/v2020_01_01
```

### Tag: package-2017-06 and python

These settings apply only when `--tag=package-2017-06 --python` is specified on the command line.
Please also specify `--python-sdks-folder=<path to the root directory of your azure-sdk-for-python clone>`.

``` yaml $(tag) == 'package-2017-06' && $(python)
python:
  namespace: azure.mgmt.domainservice.v2017_06_01
  output-folder: $(python-sdks-folder)/domainservices/azure-mgmt-domainservices/azure/mgmt/domainservices/v2017_06_01
```

### Tag: package-2017-01 and python

These settings apply only when `--tag=package-2017-01 --python` is specified on the command line.
Please also specify `--python-sdks-folder=<path to the root directory of your azure-sdk-for-python clone>`.

``` yaml $(tag) == 'package-2017-01' && $(python)
python:
  namespace: azure.mgmt.domainservice.v2017_01_01
  output-folder: $(python-sdks-folder)/domainservices/azure-mgmt-domainservices/azure/mgmt/domainservices/v2017_01_01
```
