<!--
SPDX-License-Identifier: Apache-2.0 WITH LLVM-exception
-->

# The Beman Process

This document specifies stages and best practices for Beman Project libraries development. Its goal is to create consistency facilitating the evaluation of, and contribution to Beman libraries.

## Introduction

### Changing this document

This is a living document that adapts to evolving best practices and community
needs. To make changes:

1. Create a [discourse topic](https://discourse.boost.org) detailing the change
   and how it aligns with the core principles.
2. After some community discussion, create a PR with the actual change on
   [GitHub](https://github.com/bemanproject/beman) with a *leads question*
   label. The PR should also link to the discourse topic.
3. Continue discussions on the PR and discourse topic.
4. Await a leads a decision based on the community feedback.

## Beman libraries lifetime

We aim to provide to support the efficient design and adoption of the highest
quality C++ Standard libraries through implementation experience,
user feedback, and technical expertise. Until a library reaches a stable
production-ready status,it can have various changes which are listed below.

The Beman libraries possible status are:

1. `BEMAN DEVELOPMENT`:
    * The target paper(s) may change within the ISO standardization stages, thus also the implementation.
    * Design changes are expected in this stage.
    * The testing may be incomplete in this stage.
2. `BEMAN UNSTABLE`:
    * The paper(s) may be still pending for final ISO C++ Standardization review, but yet in a possible shape.
    * The library implementation matches the paper(s), but needs more testing and possible more updates to be Beman Standard conformant.
3. `BEMAN STABLE`:
    * All target papers were accepted into the ISO C++ Working Draft - no possible design changes expected here.
    * All papers were implemented in the current Beman library.
    * The testing is completed.
    * The code is production ready.
    * Only bugfixes expected in this stage. Any other addition to the same utility (e.g., adding another C++29 std::optional extension on top of C++26 std::optional) would be done into a new Beman library / repo.
    * A `BEMAN STABLE` library keeps its status for 2 C++ development cycles. At that point, it is expected that all major compiler vendors will already have a standard conformant implementation, so all users can switch from the Beman library to the Standard Library.
      * e.g., `beman.optional26` is kept until C++26 and C++29 standards are released. We will deprecated `beman.optional26` when the final C++29 Draft is released (e.g. probably in 2029-2030).
4. `BEMAN DEPRECATED`: Such Beman library was used as an intermediate solution (check `BEMAN STABLE`) and when all major compiler vendors provided an implementation, this library serves no purpose.

## Bemanification

If a new repo needs to be bemanified (apply the [Beman Standard](https://github.com/beman-project/beman/blob/main/docs/BEMAN_STANDARD.md)), it is recommended to create a new issues with next description to track the progress (example - [beman.exemplar issue #14](https://github.com/bemanproject/exemplar/issues/14)).

Please update the template in this document if outdated! Use the following style:

```mardkdown
Apply the [Beman Standard](https://github.com/beman-project/beman/blob/main/docs/BEMAN_STANDARD.md).

...

# Updates tracker
## License
- [ ] LICENSE.APPROVED
- [ ] LICENSE.APACHE_LLVM
- [ ] LICENSE.CRITERIA
 
## General

- [ ] LIBRARY.NAMES
- [ ] REPOSITORY.NAME
- [ ] REPOSITORY.CODEOWNERS

## Top-level

- [ ] TOPLEVEL.CMAKE
- [ ] TOPLEVEL.LICENSE
- [ ] TOPLEVEL.README

## README.md

- [ ] README.TITLE
- [ ] README.PURPOSE
- [ ] README.IMPLEMENTS
- [ ] README.LIBRARY_STATUS

## CMake

- [ ] CMAKE.DEFAULT
- [ ] CMAKE.PROJECT_NAME
- [ ] CMAKE.LIBRARY_NAME
- [ ] CMAKE.LIBRARY_ALIAS
- [ ] CMAKE.TARGET_NAMES
- [ ] CMAKE.CONFIG
- [ ] CMAKE.SKIP_TESTS
- [ ] CMAKE.SKIP_EXAMPLES
- [ ] CMAKE.AVOID_PASSTHROUGHS

## Directory Layout

- [ ] DIRECTORY.INTERFACE_HEADERS
- [ ] DIRECTORY.IMPLEMENTATION_HEADERS
- [ ] DIRECTORY.SOURCES
- [ ] DIRECTORY.TESTS
- [ ] DIRECTORY.EXAMPLES
- [ ] DIRECTORY.DOCS
- [ ] DIRECTORY.PAPERS

## File contents

- [ ] FILE.NAME
- [ ] FILE.TEST_NAMES
- [ ] FILE.LICENSE_ID
- [ ] FILE.COPYRIGHT

## C++

- [ ] CPP.NAMESPACE

```
