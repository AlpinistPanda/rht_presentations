---
theme: default
title: Resilient Hydro Twin – System Updates
info: Recent Platform Improvements
class: text-center
highlighter: shiki
transition: slide-left
---
 
# Resilient Hydro Twin  
## Platform Updates Overview

--- 

# Authentication

## What changed?

- Users can now **create accounts**
- Users can **log in and log out securely**
- The system remembers your session
- New users are **not immediately active**

## Why this matters

- Ensures **controlled access**
- Supports **multi-user environments**
- Prepares the system for **real deployment**

---

# User Approval Workflow

## What changed?

- New users must be **approved by an admin**
- Admins can:
  - View pending users
  - Approve or reject accounts

## What users experience

- If not approved yet → clear message:  
  “Your account is pending approval”

## Why this matters

- Prevents misuse
- Enables **institutional control**
- Supports **project-based access management**

---

# Admin Features

## What changed?

- New **admin dashboard**
- Dedicated pages for:
  - User approvals
  - Intervention management
- Admin tools integrated into the system

## Why this matters

- Makes the platform **manageable at scale**
- Enables **governance and oversight**
- Reduces need for manual backend work

---

# Planning Interface Improvements

## What changed?

- Cleaner layout:
  - Removed cluttered navigation tabs
  - Introduced focused **planning interface**
- New **Interventions & Scenarios tabs**
- Improved map interaction

## Why this matters

- More intuitive workflow
- Better focus on **planning tasks**
- Easier for non-technical users

---

# Intervention Authoring

## What changed?

- Users can now:
  - Draw interventions directly on the map
  - Use polygons to define areas
- Drawing improved:
  - Click to start
  - Double-click to finish
  - Can create multiple interventions easily

## Why this matters

- Enables **interactive planning**
- Aligns with **real-world spatial decisions**
- Removes technical barriers

---

# Intervention Scenarios

## What changed?

- Users can group interventions into **scenarios**
- Scenarios can be:
  - Named
  - Saved
  - Exported

## Example

👉 “Flood protection plan A”  
→ Contains multiple interventions

## Why this matters

- Supports **what-if analysis**
- Enables **decision-making workflows**
- Bridges planning and simulation

---

# Raster & Simulation Outputs

## What changed?

- System can now load **TIFF simulation outputs**
- Users can:
  - Select raster layers
  - View them on the map
  - Adjust opacity

## Why this matters

- Connects planning with **model results**
- Enables **visual validation**
- First step toward **digital twin feedback loops**

---

# Backend & Data Capabilities

## What changed?

- System now stores:
  - Interventions
  - Scenarios
  - User activity logs
- APIs added for:
  - Data access
  - Scenario export
  - Raster discovery

## Why this matters

- Makes the system **data-driven**
- Enables **integration with models**
- Supports future scalability

---

# Quality & Reliability

## What changed?

- Added automated tests for:
  - Authentication
  - User approval
  - Interventions
  - Scenarios
- Fixed frontend issues
- Verified system in Docker

## Why this matters

- More **stable system**
- Fewer bugs
- Ready for **real-world usage**

---

# Key Takeaways

- Platform is now:
  - **Multi-user**
  - **Admin-controlled**
  - **Scenario-driven**
  - **Map-interactive**
  - **Simulation-aware**

---

# What’s Next?

- Integration with **flood models**
- Real-time data connections
- Advanced scenario comparison
- Stakeholder dashboards

---

# Thank You

Questions & Discussion