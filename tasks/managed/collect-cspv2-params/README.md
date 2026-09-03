# collect-cspv2-params

Tekton task that collects CSPv2 (Unified Downloads) configuration options from the data file.
This task looks at the data file in the workspace to extract params like endpoint, auth secret,
and environment configuration for downstream CSPv2 tasks.

## Parameters

| Name                    | Description                                                                                           | Optional | Default value        |
|-------------------------|-------------------------------------------------------------------------------------------------------|----------|----------------------|
| dataPath                | Path to the data JSON file in the data workspace                                                      | No       | -                    |
| snapshotPath            | Path to the JSON string of the Snapshot spec in the data workspace                                    | No       | -                    |
| ociStorage              | The OCI repository where the Trusted Artifacts are stored                                             | Yes      | empty                |
| ociArtifactExpiresAfter | Expiration date for the trusted artifacts created in the OCI repository                               | Yes      | 1d                   |
| trustedArtifactsDebug   | Flag to enable debug logging in trusted artifacts. Set to a non-empty string to enable                | Yes      | ""                   |
| orasOptions             | oras options to pass to Trusted Artifacts calls                                                       | Yes      | ""                   |
| sourceDataArtifact      | Location of trusted artifacts to be used to populate data directory                                   | Yes      | ""                   |
| dataDir                 | The location where data will be stored                                                                | Yes      | /var/workdir/release |
| taskGitUrl              | The url to the git repo where the release-service-catalog tasks and stepactions to be used are stored | No       | -                    |
| taskGitRevision         | The revision in the taskGitUrl repo to be used                                                        | No       | -                    |
| caTrustConfigMapName    | The name of the ConfigMap to read CA bundle data from                                                 | Yes      | trusted-ca           |
| caTrustConfigMapKey     | The name of the key in the ConfigMap that contains the CA bundle data                                 | Yes      | ca-bundle.crt        |
