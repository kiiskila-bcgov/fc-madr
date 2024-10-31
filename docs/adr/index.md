# Financial Components Architecture Knowledge Base

Welcome 👋 to the architecture knowledge base of the **Financial Components** project.

Here you will find all the Markdown Architectural Decision Records (MADRs) of the project.

## What Are MADRs?

An **Architectural Decision Record** (ADR) captures an important architectural decision made during the project's lifecycle, along with its context and consequences. We use **Markdown Architectural Decision Records** (MADRs), which are ADRs written in Markdown format for ease of use and accessibility.

MADRs help us document:

- **Context**: The background and reasoning behind a decision.
- **Decision**: What was decided and why.
- **Consequences**: The outcomes, both positive and negative, of the decision.

## How Do MADRs Work?

Each MADR represents a single decision. MADRs are **immutable**; only their status can change (e.g., from proposed to accepted or deprecated). By maintaining a chronological collection of MADRs, we create a decision log that documents the evolution of our project's architecture.

### The MADR Workflow

The typical workflow of a MADR is as follows:

1. **Draft**: A team member drafts a MADR using the template.
2. **Propose**: The draft is proposed for discussion.
3. **Review and Collaborate**: Team members review and provide feedback.
4. **Accept or Reject**: Based on consensus, the MADR is accepted, rejected, or modified.
5. **Record**: The final MADR is added to the decision log.

![MADR Workflow](/l4b-static/adr-workflow.png)

### Why Are MADRs Important for Financial Components?

The Financial Components project involves complex architectural decisions that impact the functionality, performance, and maintainability of our systems. Using MADRs allows us to:

- **Preserve Decision History**: Keep a record of why decisions were made, aiding future reference and onboarding.
- **Enhance Communication**: Provide clarity to all stakeholders about the reasoning behind decisions.
- **Support Compliance and Governance**: Maintain documentation that aligns with BC Government policies and standards.
- **Facilitate Collaboration**: Encourage team collaboration by involving all relevant parties in decision making.
- **Improve Project Outcomes**: Ensure informed decisions are made, reducing misunderstandings and redundant work.

## How to Use This Knowledge Base

This knowledge base is automatically updated whenever changes are made to the project's Git repository. Developers manage the MADRs directly with markdown files located alongside the code, making it convenient to keep them up-to-date.

You can browse the MADRs using the left menu or the search bar.

- **Search**: Use keywords to find MADRs on specific topics.
- **Browse by Status**: View MADRs that are proposed, accepted, deprecated, etc.
- **Chronological Order**: MADRs are organized chronologically to show the evolution of decisions.

## For Non-Technical Stakeholders

MADRs are written to be accessible to everyone involved in the project, not just developers. As a non-technical stakeholder, you can:

- **Understand Decisions**: Read MADRs to grasp why certain decisions were made.
- **Provide Feedback**: Participate in discussions during the proposal stage.
- **Stay Informed**: Keep up-to-date with the project's architectural evolution.

## Additional Resources

- **BC Government MADR Specification**: [BC MADR Specification](https://github.com/bcgov-isd/bc-madr/blob/main/bc-madr-specification.md)
- **Log4brains Documentation**: [Log4brains](https://github.com/thomvaill/log4brains)
- **Michael Nygard's Article on ADRs**: [Documenting Architecture Decisions](https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions.html)
- **ADR GitHub Organization**: [adr.github.io](https://adr.github.io/)

