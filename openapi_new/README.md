# OpenAPI Specification document for Hyper Protect Hosting Appliance

Please note that this is a Work In Progress. Not all resources and endpoints are documented, and the ones that are need some lovin'. Pull Requests are welcome!

Install the openAPI-generator: https://github.com/openapitools/openapi-generator

## Some things to try:

- Act like Travis and generate the gh_pages html:
  - `openapi-generator-cli generate -g openapi -i scaas/docs/openapi/index.json`
  - `npx redoc-cli bundle openapi.json`
  - `firefox redoc-static.html`

- Generate a single OpenAPI Specification .yaml file:
  - `openapi-generator-cli generate -g openapi-yaml -i index.json -o generated-yaml`
  - Then open the generated .yaml file in the swagger editor or swagger ui.

- Generate simple html documentation:
  - `openapi-generator-cli generate -g html -i index.json -o generated-html`
  - `firefox generated-html`

- Generate a python client like we do in the REST test suite:
  - `openapi-generator-cli generate -i index.json -g python -o hpha_python_sdk/ -DpackageName=hpha_python_sdk`

## known bugs and workarounds:
- `openapi-generator-cli` does not handle response data in `DELETE` requests. Bug opened: https://github.com/OpenAPITools/openapi-generator/issues/1734
  - a workaround for this is is to use the ``{METHOD}_with_http_data` API call and parse the results manually.
