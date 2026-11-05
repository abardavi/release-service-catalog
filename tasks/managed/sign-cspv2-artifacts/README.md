# sign-cspv2-artifacts

Sign the CSPv2 SHA256SUM manifest through the middleware-signing pipeline and add the detached signature to the release data.

## Parameters

| Name                               | Description                                                                          | Optional | Default value                                             |
|------------------------------------|--------------------------------------------------------------------------------------|----------|-----------------------------------------------------------|
| sourceDataArtifact                 | Trusted Artifact containing fetched release artifacts, README.md, and SHA256SUM.     | No       | -                                                         |
| keyname                            | Signing key name accepted by the middleware-signing pipeline.                        | No       | -                                                         |
| onbehalfof                         | Human identity requesting signing, for audit purposes.                               | No       | -                                                         |
| kerberosKeytabSecret               | Secret in the signing PipelineRun namespace containing the signing Kerberos keytab.  | No       | -                                                         |
| kerberosKeytab                     | Key within the Kerberos keytab secret.                                               | No       | -                                                         |
| kerberosPrincipal                  | Kerberos principal used by the signing pipeline.                                     | No       | -                                                         |
| signingPipeline                    | InternalRequest pipeline name for middleware signing.                                | Yes      | middleware-signing                                        |
| signingRepo                        | Git repository containing the middleware-signing task and pipeline.                  | Yes      | https://gitlab.cee.redhat.com/signing/signing.git         |
| signingRevision                    | Git revision of the signing repository to use.                                       | Yes      | main                                                      |
| signingServiceAccount              | Service account used by the internal signing PipelineRun.                            | Yes      | release-service-account                                   |
| requestTimeout                     | Maximum time in seconds to wait for the InternalRequest.                             | Yes      | 3900                                                      |
| pipelineTimeout                    | Timeout for the middleware-signing PipelineRun.                                      | Yes      | 1h0m0s                                                    |
| taskTimeout                        | Timeout for the middleware-signing TaskRun.                                          | Yes      | 0h55m0s                                                   |
| finallyTimeout                     | Timeout reserved for final tasks in the middleware-signing PipelineRun.              | Yes      | 0h5m0s                                                    |
| verbose                            | Enable verbose Kerberos diagnostics in the signing pipeline.                         | Yes      | false                                                     |
| ociStorage                         | OCI repository for Trusted Artifacts.                                                | Yes      | empty                                                     |
| ociArtifactExpiresAfter            | Expiration time for Trusted Artifacts created by this task.                          | Yes      | 1d                                                        |
| trustedArtifactsDebug              | Enable Trusted Artifacts debug logging when non-empty.                               | Yes      | ""                                                        |
| orasOptions                        | Additional oras options for Trusted Artifact operations.                             | Yes      | ""                                                        |
| trustedArtifactsDockerconfigSecret | Secret containing registry credentials for the signing pipeline's Trusted Artifacts. | Yes      | quay-token-konflux-release-trusted-artifacts-secret       |
| dataDir                            | Working directory for release data.                                                  | Yes      | /var/workdir/release                                      |
| taskGitUrl                         | Git repository URL for resolving Trusted Artifact step actions.                      | Yes      | https://github.com/konflux-ci/release-service-catalog.git |
| taskGitRevision                    | Git revision for resolving Trusted Artifact step actions.                            | Yes      | main                                                      |
| caTrustConfigMapName               | ConfigMap containing the CA bundle for Trusted Artifact operations.                  | Yes      | trusted-ca                                                |
| caTrustConfigMapKey                | Key in the CA ConfigMap containing the bundle.                                       | Yes      | ca-bundle.crt                                             |
