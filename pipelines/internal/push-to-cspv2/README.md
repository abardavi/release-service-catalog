# push-to-cspv2 pipeline

Tekton Pipeline used as an initial setup for push-to-cspv2: downloads a test
OCI artifact from Quay and verifies its checksum against the artifact's manifest.

## Parameters

| Name            | Description                                                                           | Optional | Default value                                             |
|-----------------|---------------------------------------------------------------------------------------|----------|-----------------------------------------------------------|
| taskGitUrl      | The url to the git repo where the release-service-catalog tasks to be used are stored | Yes      | https://github.com/konflux-ci/release-service-catalog.git |
| taskGitRevision | The revision in the taskGitUrl repo to be used                                        | No       | -                                                         |
