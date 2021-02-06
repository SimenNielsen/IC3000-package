# IC3000-package
## Introduction

## Specification
![Main Schema](main_schema.png)
### Backend/API
REST API (GET, POST, DELETE)
Claim
Id: int
Year: int
Name: string
Type: enum {Collision, Grounding, Bad Weather, Fire}
DamageCost: Decimal
ASP.NET Core Web application
Return appropriate http code and error messages.

### Storage
Azure Cosmos DB

### Logic restrictions
Claims that exceed 100.000 cannot be created
Year of date cannot be in the future or more than 10 years backwards

### Auditing
Push change events of claims to Azure service bus and subscribe to the queue with an azure function trigger.
