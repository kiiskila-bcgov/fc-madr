# Architecture for the ICM Error Lookup Tool

- status: accepted
- date: 2025-02-13
- **decision-makers:** Zorin Samji, Will Kiiskila
- **consulted:** Spencer Rose
- **informed:** Greg Froh, Jeremy Vernon

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

1. **JSON Export Architecture:** Use Klamm for data management with automated JSON export process
2. **Direct Klamm Integration:** Use existing Klamm (Laravel/Filament/Postgres Web Application) to manage IET data
3. **Dedicated Klamm Instance:** Create a new version of Klamm specifically for IET
4. **Independent System:** Create a separate dedicated backend/database for IET

## Decision Outcome

Chosen option: **"JSON Export Architecture" (Option 1)**, because it balances simplicity, ease of maintainability and independence from outside systems. The goal is to use Klamm to manage the data but we export the data the IET uses so it can operate independently from Klamm. This also minimizes maintenance and in the event the system data should be decoupled from Klamm it can be done easily.

### Pros and Cons

- Good, because it uses existing Klamm infrastructure for data management
- Good, because it maintains a clear separation between data management and presentation
- Good, because it eliminates the need for maintaining a separate database system
- Good, because it enables future flexibility to switch data sources without affecting the frontend
- Good, because it simplifies deployment and reduces operational complexity
- Bad, because it introduces a build/deploy step in the data update process
- Bad, because it may have slightly slower data update cycles compared to direct database access
- Bad, because it requires setting up and maintaining GitHub Actions for the export process

### Diagram

![JSON Export Architecture](/l4b-static/images/json-export-architecture.svg)

## Pros and Cons of the Other Options

### Direct Klamm Integration (Option 2)

Using the existing Klamm system directly to manage and serve IET data.

- Good, because it requires minimal initial development effort
- Good, because Klamm has long term support
- Good, because it leverages existing infrastructure and tools
- Bad, because it creates a reliance on Klamm for managing data
- Bad, because IET will always need a live connection to Klamm to function

![Direct Klamm Integration](/l4b-static/images/direct-klamm-integration.svg)

### Dedicated Klamm Instance (Option 3)

Creating a new instance of Klamm specifically for IET.

- Good, because it provides system independence
- Good, because it uses familiar tools
- Bad, because Klamm has been directed to not be split but exist as one tool for multiple teams
- Bad, because it requires maintaining a separate Klamm instance
- Bad, because it duplicates infrastructure unnecessarily

![Dedicated Klamm Instance](/l4b-static/images/dedicated-klamm-instance.svg)

### Independent System (Option 4)

Creating a completely separate backend and database for IET.

- Good, because it provides complete system independence
- Good, because it can be optimized specifically for IET needs
- Bad, because it requires more development effort
- Bad, because it requires separate database maintenance and backups
- Bad, because it adds unnecessary complexity for a simple use case
- Bad, because we are adding data that could be in Klamm in an additional location

![Independent System](/l4b-static/images/independent-system.svg)

## Confirmation

The implementation of the "JSON Export Architecture" (Option 1), can be confirmed through:

1. Successful setup of the JSON export process from Klamm
2. Verification of the GitHub Actions workflow for automated data updates
3. Unit test and end-to-end testing of the entire process
4. Documentation review of the data update process

## More Information

The JSON export architecture provides an approach that balances our immediate needs with future flexibility. We also have the need to send feedback to Klamm or another system. All the approaches can handle this need in different ways. For a long term solution of gathering feedback across multiple systems we should look at tools purpose built for that rather than adapting Klamm further to handle that use case.
