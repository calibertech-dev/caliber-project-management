# Caliber Project Management

Caliber Project Management is a comprehensive project tracking and execution module built for the **Caliber Platform**.  
It extends Salesforce to provide structured workflows for managing **projects**, **phases**, **field reports**, **measurements**, and **site conditions**—enabling complete visibility and control from proposal through fulfillment.

---

## Overview

This package acts as the operational hub connecting **Opportunities**, **Proposals**, **Contracts**, **Work Orders**, and **Invoices** under a unified **Project** record.  
It introduces standardized project hierarchies, daily reporting, measurement tracking, and condition logging to make field operations traceable, auditable, and tightly linked to the Caliber Commerce lifecycle.

Caliber Project Management is designed for flexibility across industries such as construction, restoration, inspection, and field service—and integrates seamlessly with all Caliber Platform modules.

---

## Core Features

- **Project Hub** – Centralized record linking all commercial and operational data, including Proposals, Contracts, Work Orders, and Invoices.  
- **Phases** – Break projects into structured milestones with planned vs. actual tracking, progress percentages, and completion triggers.  
- **Daily Reports** – Capture on-site progress, hours, conditions, photos, and technician notes directly from the field.  
- **Measurements** – Record environmental or technical readings (e.g., temperature, humidity, amperage, pressure) using dependent Metric → Unit picklists.  
- **Conditions** – Log safety issues, environmental observations, or site concerns with severity and resolution tracking.  
- **Project Billing Lines** – Connect Proposal or Estimate lines to Project Phases to enable progress and milestone-based billing.  
- **Change Orders & Amendments** – Integrate directly with Caliber Commerce Contract Amendments and Change-type Proposals for scope modifications.  
- **Dashboards & Reports** – Prebuilt analytics for project progress, open conditions, and completion timelines.  
- **Automation Flows** – Declarative and Apex-assisted flows for project creation, progress roll-ups, and billing event triggers.  
- **Mobile Optimized** – Layouts and actions built for Salesforce Mobile App and Field Service Technicians.

---

## Package Dependencies

This module is part of the **Caliber Platform** ecosystem and depends on:

- **Caliber Core** – foundational utilities, error logging, and base metadata model.  
- **Caliber Commerce** – manages proposals, contracts, invoices, deposits, and billing events.

Optional extensions:
- **Caliber Restoration** – adds moisture mapping, air quality metrics, and remediation workflows.  
- **Caliber MagicPlan Integration** – imports floorplan data to automatically create projects, measurements, and proposal lines.  
- **Salesforce Field Service (optional)** – connects Projects and Phases to Work Orders and maintenance schedules.

---

## Installation & Setup

1. Install dependencies in order:
   1. `Caliber Core`
   2. `Caliber Commerce`
   3. `Caliber Project Management`
2. Assign one of the included permission sets:
   - `Caliber Project Admin`
   - `Caliber Project User`
   - `Caliber Project Read Only`
3. Add **Caliber Projects** to your App Launcher.  
4. Enable optional Flows and Reports for automation and reporting.

---

## Data Model

Caliber Project Management introduces operational objects that connect commercial and field workflows.

### Core Project Objects
| Object | Description |
|---------|-------------|
| **Project__c** | Central project record linking related business and operational objects such as Proposals, Contracts, Work Orders, and Invoices. |
| **Phase__c** | Defines key stages or milestones in a project, with planned and actual completion tracking. |
| **Project_Billing_Line__c** | Derived from Proposal Lines when the Fulfillment Route = Project. Tied to Phases for progress-based invoicing. |
| **Task__c (extension)** | Optional integration with Salesforce Tasks for assignments and to-dos related to project execution. |

---

### Field & Reporting Objects
| Object | Description |
|---------|-------------|
| **Daily_Report__c** | Field log for tracking daily site activities, crew hours, materials used, and general conditions. |
| **Measurement__c** | Captures quantitative readings such as moisture levels, temperature, voltage, or airflow. Supports Metric → Unit dependency via global value sets. |
| **Condition__c** | Records observed site issues, safety concerns, or environmental anomalies with resolution and follow-up tracking. |

---

### Change Orders & Integration Points
| Object | Description |
|---------|-------------|
| **Contract_Amendment__c (from Commerce)** | Represents approved changes to the original contract scope; linked to Change-type Proposals. |
| **Proposal__c (Type = Change)** | Drives scope and billing adjustments for projects already under contract. |
| **Invoice__c (from Commerce)** | Generated automatically when Phases marked as “Billable” or “Complete.” |

---

## Fulfillment & Billing Integration

Project Management integrates directly with Caliber Commerce for financial automation:

| Process | Trigger | Result |
|----------|----------|---------|
| **Proposal Acceptance** | Proposal.Fulfillment_Route = Project | Creates Project, Contract, and initial Invoice (Draft). |
| **Phase Completion** | Phase.Status = Complete | Generates Progress Invoice for all linked Project Billing Lines. |
| **Change Order Approval** | Contract Amendment Approved | Creates Change-type Proposal and updates Project Billing Lines. |
| **Final Invoice** | Last Phase Complete | Marks Project “Ready for Billing” and generates final invoice. |

---

## Roadmap

- Resource and equipment scheduling per phase.  
- Integrated budget vs. actual cost tracking.  
- Gantt chart and Kanban visualizations.  
- Integration with **Caliber Restoration** for condition-linked moisture maps.  
- Geolocation-based progress dashboards for Field Service mobile users.

---

## License

This project is licensed under the terms described in the [LICENSE.md](./LICENSE.md) file.

© 2025 Caliber Technologies LLC  
For commercial or implementation inquiries, contact **dev@calibertech.net**
