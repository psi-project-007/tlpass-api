# tlpass-api

> **Pre-alpha: do not store real passwords.** Nothing here has been audited yet, and the API and its data format can still change.

The TLPass API: Go handlers that run on AWS Lambda behind API Gateway. It handles sign-in and stores and returns vault data.

The API never sees a master password or a key that can decrypt. Clients encrypt everything on the device with [`@psi-project-007/tlpass-crypto`](https://github.com/psi-project-007/tlpass-crypto). The API only checks the Auth Hash and stores encrypted data, bound to the owner and the entry.

## How it fits

| Repository | Role |
| --- | --- |
| tlpass-crypto | The cryptography, published as `@psi-project-007/tlpass-crypto` |
| tlpass-web | The web portal |
| **tlpass-api** (this one) | The API (Go Lambda handlers), which stores only encrypted data |
| tlpass-infra | The AWS infrastructure (CDK in Go) that deploys this API |

## Licence

[AGPL-3.0](LICENSE).

## Security

Please don't report vulnerabilities in public issues. Follow the [security policy](https://github.com/psi-project-007/.github/blob/main/SECURITY.md).
