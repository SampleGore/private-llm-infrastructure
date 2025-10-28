# Security Policy
Report issues via GitHub Issues or private advisory.
Hardening notes:
- Local-only networking (127.0.0.1)
- Minimal-priv containers; separate config/data volumes
- No secrets in VCS; use `.env`
- Consider image scans (Trivy) pre-pull
