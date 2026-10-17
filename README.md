# Health Club Management ERP — Systems Analysis & Design

A full systems analysis and design project for a multi-module ERP built for a health club/fitness facility, covering requirements engineering, data modeling, system architecture, and phased implementation planning.

## Project Overview

Buch Athletics, a health club management business, needed to replace fragmented manual processes (spreadsheet-based membership tracking, manual billing, paper scheduling) with an integrated ERP system. I was engaged as the business systems analyst responsible for eliciting requirements, modeling the system's data and processes, evaluating architecture options, and producing a phased rollout plan that prioritized revenue-critical functionality first.

**Methodology reference**: Kendall & Kendall, Systems Engineering Analysis and Design, 11th Ed.

## Business Problem

The client was losing revenue to manual billing errors and missed renewals, had no centralized source of truth for member data, and lacked visibility into facility utilization and operational performance. The goal was a single integrated ERP covering financial management, member management, staff/HR operations, facility booking, member engagement, and analytics, sequenced to deliver ROI early rather than attempting a large scale deployment.

## Proposed Solution

- **Requirements elicitation:** Gathered and documented functional and non-functional requirements across membership, billing, scheduling, HR, and facility-management modules.
- **Data modeling:** Designed entity-relationship models (ERDs) and data flow diagrams (DFDs) covering 17 core entities — Member, Billing, Booking, Employee, Expense, Feedback, Loyalty, and more — with full field-level detail and defined relationships.
- **Process modeling:** Mapped end-to-end workflows for the system's most complex operations, including the membership billing cycle, concurrent facility booking with waitlist handling, and an expense fraud-detection pipeline.
- **Architecture design:** Recommended a three-tier architecture with a service-oriented integration layer (microservices per module, API gateway, message queue for async tasks), evaluated open-source module integration (Frappe HR) against custom build, and specified a full technology stack with rationale.
- **Risk and compliance analysis:** Produced a formal risk register and defined security/compliance controls, including PCI-DSS payment handling and an immutable audit trail for financial transactions.
- **Implementation planning:** Sequenced delivery into four milestones — Core Infrastructure & Revenue Operations, Operational Efficiency & Staff Management, Member Engagement & Experience, and Ancillary Revenue & Analytics — with a change management and data migration plan, plus KPIs to track post-launch success.

## Key Artifacts

| Artifact | Description |
|---|---|
| [Full ERP Specification](documentation/ERP_Specification.md) | 16-section end-to-end systems design document: scope, requirements, architecture, data dictionary, workflows, risk register, roadmap, KPIs |
| [Entity Relationship Diagram](diagrams/erp_erd.png) | Full data model covering all core entities and relationships |
| [Original Milestone Structure](documentation/Improved_ERP_Milestone_Structure.docx) | Source planning document defining the phased rollout strategy |

## System Design Highlights

**Architecture:** Three-tier design (React/React Native presentation layer, microservices application layer via REST APIs, PostgreSQL + MongoDB + Redis data layer) with an SOA integration layer connecting third-party payment gateways, SMS, and biometric hardware.

**Data model:** 17 entities spanning members, billing, staff/HR, bookings, expenses, feedback, fitness tracking, loyalty, and POS/inventory — see the ERD above.

**Notable process design:** The facility booking workflow uses a Redis-cached availability check with asynchronous queue-based confirmation to prevent double-booking under concurrent demand, with automatic waitlist promotion and refund handling on cancellation.

## Projected Business Impact

| Metric | Target |
|---|---|
| Member check-in time | Under 15 seconds (vs. 2–3 minutes manual) |
| Billing error rate | Under 1% (vs. ~10% manual) |
| Staff admin time | 30% reduction |
| Member retention rate | +15% |
| Café/retail revenue per member | +20% |

## Tech Stack Evaluated

Node.js/Express or Python/Django (backend) · React + Next.js (frontend) · React Native (mobile) · PostgreSQL + Redis (data layer) · MongoDB (unstructured data) · Docker + GitHub Actions (CI/CD)

## Skills Demonstrated

Requirements gathering · Business process mapping · Data modeling (ERD/DFD) · Systems architecture design · Risk analysis · Stakeholder communication · Technical documentation · Change management planning

---

*This repository contains analysis and design documentation only; it does not include a working implementation. All artifacts were produced as part of a real client engagement.*
<img width="468" height="653" alt="image" src="https://github.com/user-attachments/assets/e5610f41-bec7-469d-8727-37be07a6c8d5" />
