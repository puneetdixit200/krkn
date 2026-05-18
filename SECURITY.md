# Security Policy

We attach great importance to code security. We are very grateful to the users, security vulnerability researchers, etc. for reporting security vulnerabilities to the Krkn community. All reported security vulnerabilities will be carefully assessed and addressed in a timely manner.


## Vulnerability Remediation History

### 2026-05-15: Major Dependency Upgrade

Fixed 130+ vulnerabilities by upgrading core dependencies:

#### Critical (3 CVEs - ALL FIXED)
- **CVE-2025-22871**: Go stdlib → Upgraded to Go 1.26.3
- **CVE-2026-27143**: Go stdlib → Upgraded to Go 1.26.3  
- **CVE-2025-68121**: Go stdlib → Upgraded to Go 1.26.3

#### High Severity (50+ - ALL FIXED)
- **Python packages:**
  - GHSA-9hjg-9r4m-mvj7: requests 2.31.0 → 2.32.4
  - GHSA-9wx4-h78v-vm56: requests 2.31.0 → 2.32.4
  - GHSA-gc5v-m9x4-r6x2: requests 2.31.0 → 2.33.0+
  - GHSA-qccp-gfcp-xxvc: urllib3 2.6.3 → 2.7.0
  - GHSA-8rrh-rw8j-w5fx: wheel 0.44.0 → 0.46.2
  - GHSA-58pv-8j8x-9vj2: jaraco-context 5.3.0 → 6.1.0
  - GHSA-3c37-wwvx-h642: cbor2 5.6.5 → 5.9.0

- **Go modules:**
  - GHSA-4c29-8rgm-jvjj: moby/buildkit v0.12.5 → v0.28.1
  - GHSA-f2g3-hh2r-cwgc: distribution/distribution → v3.1.1
  - GHSA-f83f-xpx7-ffpw: sigstore/fulcio → v1.8.5
  - GHSA-273p-m2cw-6833: sigstore/rekor → v1.5.0
  - GHSA-389r-gv7p-r3rp: go-git/go-git → v5.19.0
  - GHSA-qw64-3x98-g7q2: go-git/go-billy → v5.9.0
  - GHSA-78h2-9frx-2jm8: go-jose/go-jose/v4 → v4.1.4
  - GHSA-pc3f-x583-g7j2: moby/spdystream → v0.5.1
  - GHSA-pjcq-xvwq-hhpj: Azure/go-ntlmssp → v0.1.1
  - Plus 40+ Go stdlib CVEs fixed by Go 1.26.3

#### Breaking Changes Addressed

**docker>=7.0.0 Upgrade:**
- Removed `requests-unixsocket` dependency (Unix socket support now native in docker 7.0)
- Tested `krkn/scenario_plugins/node_actions/docker_node_scenarios.py` for compatibility
- Updated `ibm-cloud-sdk-core` to >=3.24.4 (requires requests>=2.32.4)

**Go 1.26.3 Upgrade:**
- Updated oc build (OpenShift CLI) to compile with Go 1.26.3
- Updated virtctl build (KubeVirt CLI) to compile with Go 1.26.3
- All stdlib vulnerabilities resolved


## Security Checks

Krkn leverages [Snyk](https://snyk.io/) to ensure that any security vulnerabilities found 
in the code base and dependencies are fixed and published in the latest release. Security 
vulnerability checks are enabled for each pull request to enable developers to get insights 
and proactively fix them.

 
## Reporting a Vulnerability

The Krkn project treats security vulnerabilities seriously, so we
strive to take action quickly when required.

The project requests that security issues be disclosed in a responsible
manner to allow adequate time to respond.  If a security issue or
vulnerability has been found, please disclose the details to our
dedicated email address:

cncf-krkn-maintainers@lists.cncf.io

You can also use the [GitHub vulnerability report mechanism](https://docs.github.com/en/code-security/security-advisories/guidance-on-reporting-and-writing-information-about-vulnerabilities/privately-reporting-a-security-vulnerability#privately-reporting-a-security-vulnerability) to report the security vulnerability.

Please include as much information as possible with the report. The
following details assist with analysis efforts:
  - Description of the vulnerability
  - Affected component (version, commit, branch etc)
  - Affected code (file path, line numbers)
  - Exploit code


## Security Team

The security team currently consists of the [Maintainers of Krkn](https://github.com/krkn-chaos/krkn/blob/main/MAINTAINERS.md)


## Process and Supported Releases

The Krkn security team will investigate and provide a fix in a timely manner depending on the severity. The fix will be included in the new release of Krkn and details will be included in the release notes.
