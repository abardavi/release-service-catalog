# ud2-search-test-task

Run a read-only UD2 product search and expose its output and exit code.

## Parameters

| Name                 | Description                                            | Optional | Default value   |
|----------------------|--------------------------------------------------------|----------|-----------------|
| ud2CertificateSecret | Secret containing the UD2 client certificate.          | Yes      | cspv2-stage-crt |
| ud2KeySecret         | Secret containing the UD2 client key.                  | Yes      | cspv2-crt-key   |
| caTrustConfigMapName | ConfigMap containing the trusted CA bundle.            | Yes      | trusted-ca      |
| caTrustConfigMapKey  | Key in the ConfigMap containing the trusted CA bundle. | Yes      | ca-bundle.crt   |
