# Security Policy

## Supported Versions

We support the following versions of our project with security updates:

| Version | Supported          |
| ------- | ------------------ |
| 1.x     | :white_check_mark: |

## Dependencies

This project uses the following dependencies:

- Python version 3.x
- Jupyter Notebook
- Python libraries:
  - scikit-learn
  - nltk
  - pandas
  - joblib
  - certifi

## Reporting a Vulnerability

If you discover a vulnerability in this project, please report it by creating an issue in the [issue tracker](https://github.com/powerupcyber/phishing-detection/issues) with the label "security".

Please include as much detail as possible in your report to help us identify and fix the issue promptly. This includes:

- A description of the vulnerability
- Steps to reproduce the issue
- Any potential impact of the vulnerability

We are committed to addressing security issues swiftly and will respond as soon as possible to your report.

## Best Practices

To ensure the security of your environment while using this project, we recommend the following best practices:

1. **Keep Dependencies Up-to-Date**: Regularly update Python, Jupyter Notebook, and any other dependencies to the latest versions to benefit from security patches and improvements.
2. **Use Virtual Environments**: Use Python virtual environments to manage project dependencies and isolate them from other projects on your system.
   
   - **Windows:**
     ```bash
     python -m venv venv
     venv\Scripts\activate
     ```
   - **Linux and macOS:**
     ```bash
     python3 -m venv venv
     source venv/bin/activate
     ```

3. **Limit Access**: Restrict access to your Jupyter Notebook server to trusted users and consider using password protection.
4. **Secure Data**: Ensure that any sensitive data used in your project is handled securely and not exposed in your code or notebook cells.
5. **Enable Code Security and Analysis**: We have enabled the code security and analysis feature within GitHub to help identify and fix potential security vulnerabilities in our codebase. This feature runs security checks and provides alerts for any issues found.

Thank you for helping us keep this project secure!
