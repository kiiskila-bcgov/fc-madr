[//]: # "bc-madr v0.1.0"

<!-- modified MADR 4.0.0 -->

# Use BC Gov implementation of MADR

- status: proposed <!-- proposed | rejected | accepted | deprecated | ... | superseded by ADR-0123 -->
- date: 2024-10-31 <!-- YYYY-MM-DD when the decision was last updated -->
- decision-makers: Will Kiiskila<!-- list everyone involved in the decision -->
- consulted: Spencer Rose <!-- list everyone whose opinions are sought (typically subject-matter experts); and with whom there is a two-way communication --> <!-- OPTIONAL -->
- informed: Todd Scharien <!-- list everyone who is kept up-to-date on progress; and with whom there is a one-way communication} --> <!-- OPTIONAL -->

## Context and Problem Statement

We have already decided to use Markdown Architecture Decision Records as a way of tracking architecture decisions within the Financial Components stream. We need a standardized template that is simple and straightforward as people will not use it if it is complicated.

## Decision Drivers <!-- OPTIONAL -->

- The original MADR template is missing features so we would need a hacky workaround to capture all the relevent information.
- We want to use a template that is standardized within the BC Gov ecosystem so our MADRs look and feel the same.

## Considered Options

- [Use the BC Gov MADR template](https://github.com/bcgov-isd/bc-madr/blob/main/bc-madr-template.md)
- [USE original MADR Template from Log4Brains](https://github.com/thomvaill/log4brains/blob/develop/docs/adr/template.md)
- Create our own template for the Financial Components

## Decision Outcome

Chosen option: Use the BC Gov MADR template, because we would like our MADRs to have the look and feel of other BC Gov MADRs. Additionally, we prefer templates tailored to the BC Gov to ensure fields are simple and straightforward, leading to higher adoption rates within the team.

### Consequences

- Good, because our MADRs will fit in with the existing BC Gov MADR ecosystem.
- Good, because our MADRs will be completed more often if the fields are specific to our organization.
- Bad, because if the official ADR template gets updated with content we would like, it may take time for the BC Gov MADR team to update their template so we can then update ours once again.

### Confirmation <!-- OPTIONAL -->

As soon as this specific record has been published we can consider the template confirmed, since it has been written using the new template and the [template.md](https://github.com/kiiskila-bcgov/fc-madr/blob/main/docs/adr/template.md) file itself has been updated. This means anytime you run `log4brains adr new` it will utilize the new template.

## Pros and Cons of the Options <!-- OPTIONAL -->

### Use the BC Gov MADR Template

- Pros
  - Simplifies the template for better team adoption.
  - Ensures consistency with other BC Gov projects.
- Cons
  - Dependency on the BC Gov MADR team for updates.

### Use Original MADR Template from Log4Brains

- Pros
  - Widely adopted and supported.
  - Direct integration with Log4Brains.
- Cons
  - Lacks some features needed for our project.
  - May require workarounds.

### Create Our Own Template

- Pros
  - Fully customizable to our needs.
- Cons
  - akdsadjdhRequires additional effort to develop and maintain.
  - Less alignment with BC Gov standards.

## More Information

We should look to revisit this decision if the BC Gov standard MADR template changes.
