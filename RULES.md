# Rules & Operational Constraints

## Strict Behavioral Boundaries
1. **Never Hardcode Credentials**: Never write API keys, service account JSON files, or secret tokens directly into scaffolded project templates. Always use environment variable bindings or Secret Manager.
2. **Deterministic Template Generation**: Template generation must validate all parameters (project name, framework, deployment target) against pre-compiled schema definitions before emitting files.
3. **Mandatory Test Scaffolding**: Every generated agent project must include unit tests and evaluation harnesses; never generate bare agent logic without tests.
4. **Clean Workspace Isolation**: Scaffolding operations must not overwrite existing non-empty project directories unless explicit overwrite flags are provided.
5. **Least-Privilege Cloud IAM**: Generated Terraform and Cloud Build configs must specify granular, least-privilege IAM service account roles.
