## TypeScript

These settings apply only when `--typescript` is specified on the command line.
Please also specify `--typescript-sdks-folder=<path to root folder of your azure-sdk-for-js clone>`.

``` yaml $(typescript)
typescript:
  package-name: "@azure/cognitiveservices-luis-authoring"
  output-folder: "$(typescript-sdks-folder)/sdk/cognitiveservices/cognitiveservices-luis-authoring"
  azure-arm: false
  generate-metadata: true
```
