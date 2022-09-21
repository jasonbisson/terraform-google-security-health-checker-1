# Add Security Health Check to pipeline

This Cloud Build pipeline example adds a step to the [Cloud Foundation Toolkit build](https://github.com/terraform-google-modules/terraform-example-foundation/tree/master/build) to run the security health check function after deploying the infrastructure. In addition to displaying the overall security health check results, we eliminated searching multiple screens (Cloud Logging, Security Command) by adding the detailed findings to the Cloud Build log. 

## Inputs

### Cloud Build Substitutions

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| \_LOGGER\_NAME | The log name for security command center findings| `string` | `"scc_logging_test_${BUILD_ID}"' | yes |
| \_CRITICAL | The number of critical findings before failing the build | `string` | 0 | yes |
| \_HIGH | The number of high findings before failing the build | `string` | 10 | yes |
| \_MEDIUM | The number of medium findings before failing the build | `string` | 20 | yes |
| \_FUNCTION_NAME| The name of the security health cloud function  | `string` | '"scc_helper_updated"' | yes |
| \_FUNCTION_PROJECT_ID | The project id hosting security health cloud function  | `string` | n/a | yes |
| \_SCOPED_PROJECT | The project id being checked for insecure infrastructure findings  | `string` | n/a | yes | 