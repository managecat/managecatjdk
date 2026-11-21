# ManageCat JDK

**Independent OpenJDK-based security-maintenance builds maintained by ManageCat LLC.**

ManageCat JDK is an OpenJDK-derived distribution developed to provide security updates to enterprise users when a relevant upstream fix is available but an official Eclipse Temurin binary containing that fix is not yet available for the required platform. ManageCat builds and validates its own binaries under the **ManageCat JDK** name. When the corresponding official Eclipse Temurin release becomes available, customers may transition to it.

> **Independent distribution.** ManageCat JDK is not an official Eclipse Temurin or Oracle JDK release. It is not endorsed by Eclipse Adoptium, the Eclipse Foundation, or Oracle. No Java SE TCK/JCK certification or compatibility claim is made for any build unless its release documentation specifically identifies the completed testing and the basis for that claim.

## Source code and relationship to Eclipse Temurin

The Java implementation source code used for ManageCat JDK originates from the **OpenJDK project**. Eclipse Temurin is also built from OpenJDK source code. Eclipse Adoptium maintains mirrors of the upstream OpenJDK repositories and uses its own build and release infrastructure to create official Temurin binaries.

For each ManageCat JDK build, our intended approach is to:

1. Identify the OpenJDK source tag or commit corresponding to a relevant officially released Eclipse Temurin version, using available release provenance.
2. Obtain the OpenJDK source directly from the upstream OpenJDK repository or an Eclipse Adoptium mirror of that repository.
3. Apply the publicly available upstream security fixes needed for the affected Java version, including carefully reviewed backports when necessary.
4. Compile an independently branded ManageCat JDK binary and perform applicable release validation.
5. Record the source revision, applied patches, build configuration, target platform, and test results in the build's release notes.

For example, source repositories for the JDK 17 update line include:

- Upstream OpenJDK: https://github.com/openjdk/jdk17u
- Eclipse Adoptium mirror: https://github.com/adoptium/jdk17u

Using an Eclipse Adoptium source mirror does not make the resulting binary an Eclipse Temurin release. We do not represent our independently built artifacts as official Temurin binaries.

## When a ManageCat JDK security build is considered

A build may be prepared when:

1. A relevant JDK security vulnerability and its corresponding fix have been publicly disclosed or made available upstream.
2. The official Eclipse Temurin binary containing the fix is not yet available for the required Java version, operating system, or architecture.
3. An affected customer has a confirmed or reasonably established exposure that warrants an earlier update.
4. The change can be implemented, reviewed, and validated for the intended platform.

When an appropriate official Eclipse Temurin update is already available, using that update is generally preferred.

## Build identity and release information

ManageCat JDK uses independent product naming and ManageCat vendor information. Published release notes will identify the exact JDK version and build identifier rather than suggesting that a ManageCat build is an official Temurin release.

For each distributed build, we intend to document:

- Java/OpenJDK version, source repository, and pinned source tag or commit.
- Relevant CVE identifiers and the specific upstream fix commits or patches included.
- Build toolchain, significant configuration options, target OS, and architecture.
- Release artifact hashes, including SHA-256.
- Testing performed, results, known limitations, and any documented exceptions.
- Corresponding source code and applicable third-party license notices.

## Validation and quality assurance

Our release-validation process is intended to include applicable **Eclipse Adoptium AQAvit** test suites, OpenJDK **jtreg** regression tests, smoke tests, and targeted checks for the security changes being delivered. Customer application testing is also recommended before production deployment.

Each release will report the tests actually run and their results. Running selected AQAvit tests does not itself establish formal AQAvit product verification, Java SE compatibility, or TCK/JCK certification. We will not represent a build as certified or verified unless the applicable requirements have been satisfied and any necessary rights to make the claim have been obtained.

AQAvit project: https://github.com/adoptium/aqa-tests

## Transition to official Eclipse Temurin

ManageCat JDK security builds are intended to address time-sensitive security needs. Once Eclipse Adoptium publishes an appropriate official Temurin release containing the relevant fix, customers may evaluate and adopt that release according to their own change-management procedures.

## Licensing and source availability

OpenJDK source code is generally licensed under **GPL version 2 with the Classpath Exception**, subject to the applicable license texts and notices. Some incorporated components and build tools may carry other open-source licenses.

ManageCat will provide the corresponding source code, modifications, attribution, and license notices required for any binaries it distributes. Commercial support services are offered separately and do not limit rights granted by the applicable open-source licenses.

## Open-source collaboration

ManageCat LLC intends to contribute generally applicable bug fixes, security improvements, and compatibility enhancements upstream where appropriate, following the applicable OpenJDK contribution processes and responsible security disclosure practices.

## Project status

This repository currently contains project documentation. Build automation, validation tooling, release documentation, and distributable artifacts will be published as they become available. References to planned processes are not claims that a particular build has already passed those tests.

For commercial Eclipse Temurin support, see https://www.managecat.com.
