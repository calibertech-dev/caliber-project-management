# Caliber Project Management

Caliber Project Management is a comprehensive project tracking and execution module built for the **Caliber Platform**.  
It extends Salesforce to provide structured workflows for managing projects, phases, field reports, measurements, and site conditions—enabling both operational visibility and process control.

## Overview

This package acts as the central hub connecting operational objects such as **Work Orders**, **Opportunities**, **Proposals**, **Contracts**, and **Invoices** to a unified **Project** record.  
It introduces standardized project structures, daily reporting, measurement tracking, and environmental condition logging to make field and restoration workflows traceable and auditable.

Caliber Project Management is designed for flexible use across industries—construction, restoration, inspection, and field service—and integrates seamlessly with other Caliber Platform modules.

## Core Features

- **Project Hub** – Serves as the parent record linking Opportunities, Quotes, Work Orders, Invoices, and Contracts.
- **Phases** – Break down complex jobs into scheduled, trackable milestones with planned vs. actual completion data.
- **Daily Reports** – Capture on-site activity, conditions, labor hours, and notes directly from technicians or managers.
- **Measurements** – Record environmental or equipment readings (e.g., temperature, humidity, pressure, electrical values) with dependent Metric → Unit picklists.
- **Conditions** – Log site issues, observations, or safety concerns with severity and resolution tracking.
- **Dashboards & Reports** – Built-in report types and visuals for project progress, open conditions, and daily activity summaries.
- **Mobile-Ready Layouts** – Compact layouts optimized for Salesforce mobile app and field service technicians.
- **Flows & Automation** – Includes declarative Flows for measurement creation, roll-ups, and project progress updates.

## Package Dependencies

This module is part of the **Caliber Platform** ecosystem and requires the following managed packages:

- **Caliber Core** – foundational utilities, error handling, and shared data model.
- **Caliber Commerce** – proposal, contract, and invoice management integration.

Optional add-ons that extend functionality:
- **Caliber Restoration** – adds moisture mapping, condition tracking, and advanced inspection data structures.
- **Caliber MagicPlan Integration (add-on)** – connects project data with floorplan capture and report generation.

## Installation & Setup

1. Install dependencies in the following order:
   1. `Caliber Core`
   2. `Caliber Commerce`
   3. `Caliber Project Management`
2. Assign one of the provided Permission Sets:
   - `Caliber Project Admin`
   - `Caliber Project User`
   - `Caliber Project Read Only`
3. Add the **Caliber Projects** Lightning App to your users’ App Launcher.
4. Optionally enable included Flows and Reports.

## Data Model

Key Custom Objects included:
- `Project__c` – Core record linking related business processes.
- `Phase__c` – Defines stages or milestones for a Project.
- `Daily_Report__c` – Field log for on-site activities and conditions.
- `Measurement__c` – Stores metric/unit/value readings.
- `Condition__c` – Tracks observations or issues identified during a project.

## Roadmap

- Integration with **Caliber Restoration** for moisture mapping.
- Resource planning and task assignment.
- Cost tracking and budget variance.
- Optional Kanban board and Gantt visualization components.

## License

This project is licensed under the terms described in the [LICENSE.md](./LICENSE.md) file.

© 2025 Caliber Technologies LLC  
For commercial or implementation inquiries, visit contact dev@calibertech.net.
