# Security Policy

## Supported Versions

| Version | Supported          |
|---------|--------------------|
| latest  | Yes                |

## Reporting a Vulnerability

If you discover a security vulnerability in this project, please report it responsibly:

1. **Do not** open a public GitHub issue for security vulnerabilities
2. Email the maintainer at the address listed in the repository profile, or use [GitHub's private vulnerability reporting](https://docs.github.com/en/code-security/security-advisories/guidance-on-reporting-and-writing-information-about-vulnerabilities/privately-reporting-a-security-vulnerability)
3. Include a description of the vulnerability, steps to reproduce, and any potential impact
4. Allow reasonable time for a fix before public disclosure

## Scope

This project consists of local CLI scripts that generate documents from JSON input. The primary security considerations are:

- **Supply chain:** Dependency integrity for `python-docx`, `fpdf2`, and `python-pptx`
- **File handling:** The scripts read local JSON configs and write local document files
- **DOCX-to-PDF conversion:** The `--docx` flag in `generate_gdd_pdf.py` delegates to external software (Microsoft Word or LibreOffice). Only use this with trusted `.docx` files — do not process untrusted or user-uploaded documents through this path

## Security Practices

- Dependencies are pinned to exact versions in `requirements.txt`
- No networking, authentication, or server endpoints are implemented
- No secrets or API keys are required or stored
- `.gitignore` excludes IDE settings and local config files

## Auditing Dependencies

```bash
pip install pip-audit
pip-audit -r requirements.txt
```
