# push-to-cspv2

Tekton task that creates an InternalRequest to run an initial setup for
push-to-cspv2: downloading a test OCI artifact from Quay and verifying its checksum.

## Parameters

| Name            | Description                                                                                           | Optional | Default value |
|-----------------|-------------------------------------------------------------------------------------------------------|----------|---------------|
| pipelineRunUid  | The uid of the current pipelineRun. Used as a label value when creating internal requests             | No       | -             |
| taskGitUrl      | The url to the git repo where the release-service-catalog tasks and stepactions to be used are stored | No       | -             |
| taskGitRevision | The revision in the taskGitUrl repo to be used                                                        | No       | -             |
| requestTimeout  | InternalRequest timeout                                                                               | Yes      | 1800          |
