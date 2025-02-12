# Architecture for the ICM Error Lookup Tool

- **decision-makers:** Zorin Samji, Will Kiiskila
- **consulted:** Spencer Rose
- **informed:** TBD (Greh Froh)

## Context and Problem Statement

We need to build a simple web application, the ICM Error Lookup Tool (IET), that allows users to look up Integrated Case Management (ICM) error messages and retrieve helpful information. While the frontend requirements are straightforward, we need to determine the most effective way to manage, serve, store and maintain the error message data. The challenge is avoiding tying the project to existing systems such as Klamm and minimize ongoing maintenance such as database backups.

## Decision Drivers

- Long term maintainability and simplicity of the system
- Desire to minimize operational maintenance
- Potential need for system independence from Klamm in the future
- Ease of data management for managing error message content
- System reliability and performance
- Development and maintenance effort required

## Considered Options

- **Direct Klamm Integration:** Use existing Klamm (Laravel/Filament/Postgres Web Application) to manage IET data
- **Dedicated Klamm Instance:** Create a new version of Klamm specifically for IET
- **Independent System:** Create a separate dedicated backend/database for IET
- **JSON Export Architecture:** Use Klamm for data management with automated JSON export process

## Decision Outcome

**Chosen option:** "JSON Export Architecture", because it balances simplicity, ease of maintainability and independence from outside systems. The goal is to use Klamm to manage the data but we export the data the IET uses so it can operate independently from Klamm. This also minimizes maintenance and in the event the system data should be decoupled from Klamm it can be done easily.

### Consequences

- Good, because it leverages existing Klamm infrastructure for data management
- Good, because it maintains a clear separation between data management and presentation
- Good, because it eliminates the need for maintaining a separate database system
- Good, because it enables future flexibility to switch data sources without affecting the frontend
- Good, because it simplifies deployment and reduces operational complexity
- Bad, because it introduces a build/deploy step in the data update process
- Bad, because it may have slightly slower data update cycles compared to direct database access
- Bad, because it requires setting up and maintaining GitHub Actions for the export process

## Pros and Cons of the Options

### Direct Klamm Integration

Using the existing Klamm system directly to manage and serve IET data.

- Good, because it requires minimal initial development effort
- Good, because it leverages existing infrastructure and tools
- Bad, because it creates a reliance on Klamm from IET

### Dedicated Klamm Instance

Creating a new instance of Klamm specifically for IET.

- Good, because it provides system independence
- Good, because it uses familiar tools
- Bad, because it requires maintaining a separate Klamm instance
- Bad, because it duplicates infrastructure unnecessarily

### Independent System

Creating a completely separate backend and database for IET.

- Good, because it provides complete system independence
- Good, because it can be optimized specifically for IET needs
- Bad, because it requires more development effort
- Bad, because it requires separate database maintenance and backups
- Bad, because it adds unnecessary complexity for a simple use case

### JSON Export Architecture

Using Klamm for data management with automated JSON export process.

- Good, because it uses existing Klamm for content management
- Good, because it enables simple, static hosting of the lookup tool (no backend needed)
- Good, because it allows for future flexibility in data sources
- Bad, because it requires setting up and maintaining an export process
- Bad, because it introduces a slight delay in data updates
- Neutral, because it requires setting up GitHub Actions but simplifies ongoing operations

### Confirmation

The implementation can be confirmed through:

1. Successful setup of the JSON export process from Klamm
2. Verification of the GitHub Actions workflow for automated data updates
3. Unit test and end-to-end testing of the entire process
4. Documentation review of the data update process

## More Information

The JSON export architecture provides an approach that balances our immediate needs with future flexibility. We also have the need to send feedback to Klamm or another system. All the approaches can handle this need in different ways. For a long term solution of gathering feedback across multiple systems we should look at tools purpose built for that rather than adapting Klamm further to handle that use case.
