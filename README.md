# Financial Components Architecture Decision Records

Welcome to the Architecture Decision Records (ADRs) repository for the **Financial Components** stream of the Application Modernization Program (AMP) in the Information Services Divison (ISD) of the Ministry of Social Development and Poverty Reduction (SDPR) for the Government of British Columbia.

This repository contains all the architectural decisions made during the development of the Financial Components. ADRs help us document significant decisions that shape our project.

## Viewing the ADRs

ADRs are automatically published to our Log4brains architecture knowledge base:

🔗 **[Financial Components ADRs Knowledge Base](https://kiiskila-bcgov.github.io/fc-madr/log4brains/)**

Please use this link to browse and read the ADRs.

## Development

### Prerequisites

- **Node.js**: Ensure you have Node.js installed. Download it from [nodejs.org](https://nodejs.org/).
- **Log4brains**: Install Log4brains globally if you haven't already.

### Installing Log4brains

```bash
npm install -g log4brains
```

### Previewing the Knowledge Base Locally

To preview the ADRs locally with hot-reloading enabled:

```bash
log4brains preview
```

In preview mode, any changes you make to a markdown file are automatically reflected in the UI.

### Creating a New ADR

To create a new ADR interactively:

```bash
log4brains adr new
```

Follow the prompts to fill in the details of your ADR.

## Contributing

We welcome contributions from all team members. To contribute:

**1. Clone the Repository**

```bash
git clone https://github.com/kiiskila-bcgov/fc-madr.git
```

**2. Navigate to the Repository**

```bash
cd fc-madr
```

**3. Create a New Branch**

```bash
git checkout -b your-branch-name
```

Replace your-branch-name with a descriptive name for your branch.

**4. Make Changes**

- Add or edit ADRs using Log4brains.
- Follow the MADR template located in docs/decisions.

**5. Commit Your Changes**

```bash
git add .
git commit -m "Add ADR for [decision title]"
```

**6. Push to GitHub**

```bash
git push origin your-branch-name
```

**7. Create a Pull Request**

- Go to the repository on GitHub.
- Click on "Compare & pull request".
- Provide a description of your changes and submit the pull request.

## More Information

- [Log4brains Documentation](https://github.com/thomvaill/log4brains/tree/master#readme/)
- [What is an ADR and Why Should You Use Them](https://github.com/thomvaill/log4brains/tree/master#-what-is-an-adr-and-why-should-you-use-them)
- [ADR GitHub Organization](https://adr.github.io/)
- [BC Government MADR Specification](https://github.com/bcgov-isd/bc-madr/)
