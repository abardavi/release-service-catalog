# push-to-cspv2-task

Internal task used as an initial setup for the push-to-cspv2 pipeline: it
downloads a small public OCI artifact from Quay with oras and verifies the
downloaded file's checksum matches the digest declared in the artifact's manifest.
This does not implement any CSPv2-specific logic; it's a basic starting point for
future development.

## Parameters

| Name        | Description                                                              | Optional | Default value               |
|-------------|--------------------------------------------------------------------------|----------|-----------------------------|
| artifactRef | The OCI artifact reference to download with oras, used as a test fixture | Yes      | quay.io/podman/hello:latest |
