<!--
Sync Impact Report
Version change: unversioned scaffold → 1.0.0 (initial adoption)
Modified principles:
- Unfilled principle 1 → I. Training-Only Purpose and Honest Scope
- Unfilled principle 2 → II. Local-First and Replaceable Infrastructure
- Unfilled principle 3 → III. Identity, Authorization, and User Isolation
- Unfilled principle 4 → IV. Layered ASP.NET Core Design
- Unfilled principle 5 → V. Verifiable Changes
Added sections: Additional Constraints; Development Workflow
Removed sections: None
Follow-up TODO: Confirm the original ratification date with project owners.
-->
# ContosoDashboard Constitution

## Core Principles

### I. Training-Only Purpose and Honest Scope
ContosoDashboard MUST remain clearly identified as a fictional training application and MUST NOT
be represented as production-ready. Documentation and examples MUST disclose material training
limitations, especially the mock authentication model and local-only service assumptions.
Production identity, compliance, reliability, and security guarantees MUST NOT be implied.
This keeps learners and downstream users from mistaking demonstration code for a deployable
business system.

### II. Local-First and Replaceable Infrastructure
The application MUST remain usable for its training purpose in a local, offline environment
without requiring cloud accounts or external service dependencies. Infrastructure dependencies
intended to vary between environments MUST use the repository's existing interfaces and
dependency-injection patterns where practical. Changes MUST NOT make a cloud provider mandatory
for ordinary training use.
This preserves predictable, low-friction training while allowing infrastructure concepts to be
taught through replaceable implementations.

### III. Identity, Authorization, and User Isolation
Protected application pages MUST require authentication. Operations over user- or
project-scoped data MUST enforce role and resource authorization in the service layer, not rely
only on UI visibility or route checks. New or changed access rules MUST include verification
that an unauthorized user cannot read or modify the protected resource. Mock authentication
MUST remain explicitly training-only and MUST NOT be described as a production identity system.
These controls teach defense in depth and protect the training app's user-isolation behavior.

### IV. Layered ASP.NET Core Design
Application pages and components MUST delegate business operations to services; services MUST
use the data layer rather than placing database operations in presentation code. Dependencies
MUST be registered through dependency injection and service contracts MUST be preserved when
changing implementations. Changes MUST follow the existing ASP.NET Core, Blazor Server,
Entity Framework Core, and SQL Server LocalDB patterns unless an approved feature specification
defines a deliberate migration.
This separation keeps the training code understandable and makes implementation choices
replaceable and reviewable.

### V. Verifiable Changes
Every behavior change MUST include automated tests at the applicable layer when a test
project or suitable test harness exists. If no applicable automated test infrastructure exists,
the change proposal or review MUST record reproducible manual verification steps. Changes MUST
build successfully, and security-sensitive changes MUST verify both allowed and denied access
paths. User-facing behavior or setup changes MUST update the relevant documentation.
These checks make changes reviewable and help learners see how requirements are validated.

## Additional Constraints

- The baseline application is ASP.NET Core 10 with Blazor Server, Entity Framework Core, and
  SQL Server LocalDB. Framework or persistence changes MUST be specified and reviewed rather
  than introduced incidentally.
- Training use MUST remain local-first and must not require external service credentials.
- Any production-migration example MUST clearly distinguish a suggested future implementation
  from functionality that is actually present in this training repository.

## Development Workflow

- Feature work MUST follow the repository's Spec-Driven Development workflow: define the
  requirement and acceptance criteria before implementation, then plan and track the work using
  the applicable Spec Kit artifacts.
- Before review, contributors MUST run the relevant build and available tests, verify acceptance
  criteria, and include manual verification steps when automated coverage is unavailable.
- Reviews MUST check scope, authorization and user isolation where relevant, and consistency
  between behavior and documentation. Unrelated changes MUST remain untouched.

## Governance

This constitution governs feature specifications, plans, implementation, and reviews in this
repository. Amendments MUST be made in a reviewed change that states the rationale and impact.
The amendment MUST update the version and last-amended date, and MUST identify compatibility
effects and any required follow-up work. Project maintainers approve amendments.

Constitution versions use semantic versioning. A MAJOR increment marks a backward-incompatible
governance change, including removal or redefinition of a principle. A MINOR increment marks a
new principle or section, or materially expanded requirements. A PATCH increment marks a
clarification, wording correction, or other non-semantic refinement.

Reviewers MUST assess proposed work against each applicable principle before approval. Any
exception MUST be explicit in the proposal or review, include its rationale and scope, and be
approved by project maintainers. A conflict with this constitution MUST be resolved before
implementation proceeds or the constitution is amended through the process above.

**Version**: 1.0.0 | **Ratified**: TODO(RATIFICATION_DATE): confirm original adoption date with project owners | **Last Amended**: 2026-10-30
