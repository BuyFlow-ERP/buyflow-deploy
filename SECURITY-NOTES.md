# Security notes

- Removed `backup-oke/` from the refactored package because it contained live Kubernetes Secret backups and Oracle Wallet secret data.
- Kubernetes Secret manifests are base64 encoded, not encrypted. Treat any committed secret backup as exposed.
- Use GitHub Actions Secrets, OCI Vault, or a sealed-secret/external-secret workflow for production credentials.
- If the removed Secret files were ever pushed to a remote repository, rotate DB credentials, JWT secret, and wallet material.
