# Multi-Ecosystem SCA Test Project

A single repo covering manifest files across 8 major package ecosystems, meant
for exercising SAST/SCA (Software Composition Analysis) tools against a
variety of dependency file formats in one place.

| Ecosystem | Folder            | Manifest file          |
|-----------|--------------------|-------------------------|
| npm       | `npm-project/`     | `package.json`          |
| PyPI      | `pypi-project/`    | `requirements.txt`      |
| Maven     | `maven-project/`   | `pom.xml`               |
| RubyGems  | `ruby-project/`    | `Gemfile`               |
| Go        | `go-project/`      | `go.mod`                |
| NuGet     | `nuget-project/`   | `packages.config`       |
| Composer  | `composer-project/`| `composer.json`         |
| Cargo     | `cargo-project/`   | `Cargo.toml`            |

## Notes


fq3rgrgrgfr



- Dependency versions are deliberately older/pinned real releases, chosen
  because they're widely present in public vulnerability databases (NVD,
  OSV, GitHub Advisories, Snyk, etc.) and are commonly used as SCA scanner
  test fixtures — not because every version here has been individually
  verified against a specific CVE ID. Run your scanner and let it report
  the CVEs directly against its own database rather than trusting any CVE
  claims baked into this README.
- No actual application code is included — these are manifest-only stubs.
  Add source files per subfolder if your scanner requires a buildable
  project (e.g., `mvn compile`, `npm install`, `bundle install`) rather
  than a pure manifest scan.
- To turn this into a GitHub repo:
  ```bash
  cd multi-ecosystem-sca
  git init
  git add .
  git commit -m "Initial multi-ecosystem SCA test fixtures"
  git branch -M main
  git remote add origin <your-repo-url>
  git push -u origin main
  ```
