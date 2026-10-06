# push-to-cspv2 pipeline

Tekton Pipeline for push-to-cspv2. This is an initial setup: it downloads a
test OCI artifact from Quay and verifies its checksum, as a basic starting point
for future development. CSPv2-specific artifact push logic will be added later.

## Parameters

| Name                 | Description                                                                                            | Optional | Default value                                             |
|----------------------|--------------------------------------------------------------------------------------------------------|----------|-----------------------------------------------------------|
| release              | The namespaced name (namespace/name) of the Release custom resource initiating this pipeline execution | No       | -                                                         |
| releasePlan          | The namespaced name (namespace/name) of the releasePlan                                                | No       | -                                                         |
| releasePlanAdmission | The namespaced name (namespace/name) of the releasePlanAdmission                                       | No       | -                                                         |
| releaseServiceConfig | The namespaced name (namespace/name) of the releaseServiceConfig                                       | No       | -                                                         |
| snapshot             | The namespaced name (namespace/name) of the snapshot                                                   | No       | -                                                         |
| taskGitUrl           | The url to the git repo where the release-service-catalog tasks to be used are stored                  | Yes      | https://github.com/konflux-ci/release-service-catalog.git |
| taskGitRevision      | The revision in the taskGitUrl repo to be used                                                         | No       | -                                                         |
