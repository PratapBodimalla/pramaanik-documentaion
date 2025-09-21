---
sidebar_position: 1
---

# PRD ( Product Requirement Document ) 
# PRAMAANIK.ai

> **Tagline:** *AI‑enabled, evidence‑backed, 360° professional profiling and scoring — "CIBIL score for education" — aligning education with industry needs.*

---

## Table of Contents
1. [Overview](#overview)
2. [Personas](#personas)
3. [Phase 1 Scope — Individuals (Students/Professionals)](#phase-1-scope)
   - [1) Onboarding / User Management](#onboarding)
   - [2) Data & Verification](#data-verification)
   - [3) Scoring & Progression](#scoring)
   - [4) Career Guidance](#career-guidance)
   - [5) Challenges](#challenges)
   - [6) Social](#social)
   - [7) Alerts & Notifications](#alerts)
4. [Non‑Functional Requirements (NFRs)](#nfrs)
5. [Technical Architecture (High‑Level)](#architecture)

---

## <a id="overview"></a>Overview
Pramaanik.ai is an **AI‑enabled 360° professional profiling and scoring platform**—the *“CIBIL score for education”*. It unifies **verified academic, skills, experiential, employability, entrepreneurial, and extracurricular evidence** into one **longitudinal, trusted score** to improve employability and talent discovery.

**Key highlights**
- Spans the learner journey from **Class X → professional life**
- Applies **structured 6E criteria** with weighted components
- **Multi‑stakeholder dashboards** for students, faculty, institutions, employers, and policymakers
- **Agentic AI career coach**: personalized paths, next‑best actions, gamified progress
- **Verification pipeline** (APAAR‑linked, automated checks, human‑in‑the‑loop)
- **Outcome:** transparent, evidence‑backed profiles that reduce hiring risk

---

## <a id="personas"></a>Personas
- **Individuals**: Students / Professionals  
- **Faculty**  
- **Institutions**  
- **Industry**: Recruiters & Employers  
- **Policy Makers**  
- **Admin**

> **Phase 1 focuses on the Individuals (Students / Professionals) persona.**

---

## <a id="phase-1-scope"></a>Phase 1 Scope — **Individuals (Students / Professionals)**

### <a id="onboarding"></a>1) Onboarding / User Management
**Goal:** Easy, secure access with compliance‑ready consent and trust in data usage.

**Features**
- **Sign‑up & Single Sign‑On (SSO)**  
  Create accounts with credentials or social SSO (**Google, LinkedIn, Apple**). For institutions, integrate with **Active Directory** so students use official IDs.

- **Sign‑in / Authentication (SSO)**  
  Enforce strong auth flows to safeguard identity and sensitive data.

- **Authorization (RBAC)**  
  Fine‑grained **role‑based access control**, dynamic policies, and least‑privilege permissions.

- **Central User Repository**  
  Centralized store for **identities, roles, and access rights**.

- **Consent Management**  
  Transparent capture and management of **data‑usage, verification, and sharing** consents.

---

### <a id="data-verification"></a>2) Data / Evidence Collection & Verification
**Goal:** Back every learner journey with **authentic, verifiable evidence**.

**Document Upload**
- Upload **certifications, project reports, internships, achievements**, and supporting evidence to build a **digital portfolio**.

**Document Verification**
- **Automated checks**: format, metadata, consistency  
- **Institutional verification**: college records, official sign‑offs  
- **Human‑in‑the‑loop**: for sensitive or critical records

---

### <a id="scoring"></a>3) Scoring & Progression

#### 6E Framework
- Composite **PRAMAANIK score** across: **Education, Experience, Employability, Entrepreneurship, Extracurricular, Evidence**
- **Weighted scoring** per dimension with **longitudinal tracking**
- **APAAR‑linked** verification + **human‑in‑the‑loop** checks
- **Simulation** for progression and future scenarios

#### Achievement Gallery & Badges
- Curated gallery of **validated achievements, projects, certifications, internships**
- **Badges** for milestones and evidence categories
- **Peer/social sharing** of achievements
- **Gamification**: leaderboards, streaks, challenge rewards

#### Visualization & Dashboards
- **Individual**: progress, score breakdowns, trajectory
- **Institution**: aggregated analytics, benchmarking
- **Recruiter**: candidate filtering and ranking
- **Policy makers**: demographic and skill trends
- **Simulation tools**: visualize career paths and progression

---

### <a id="career-guidance"></a>4) Career Guidance

#### Career Paths
- **AI‑generated personalized paths** aligned to **industry demand & skills taxonomy**
- **Timeline projections** for skill acquisition & milestones
- **Alternative pathways** based on emerging opportunities
- **Dynamic progression framework**: *Foundation Builder → Skill Sharpening → Expertise Expedition → Launchpad Legend*
- **Progressive missions** with increasing complexity tied to readiness

#### Career Recommendations
- **Baseline assessment** → tailored improvement opportunities
- **Skills gap analysis** mapped to industry demand & taxonomy
- **Actionable “starter mission” deck** with short‑term steps
- **Real‑time alerts**: scholarships, internships, competitions
- **AI‑driven pivots** aligned with market trends
- **Semester‑specific** goals and milestone planning

---

### <a id="challenges"></a>5) Challenges

#### Team Challenges
- Collaboration marathons; **team‑based problem solving**
- Cross‑disciplinary **project teams** with real‑world focus
- Peer mentoring & study groups with **performance tracking**
- Faculty/industry **mentor‑guided** quests

#### Competitions
- **Hackathon leaderboards** with rank‑based scoring
- **Project time‑trials** (2–3 week sprints) with deliverables
- **Innovation showcases** with peer & expert voting
- **Weekly skill duels**, mastery challenges
- **Certification races** for course validations
- **Mock interview** championships with expert judging
- **Résumé optimization** contests with review loops
- **Public speaking** & communication excellence contests

#### Events
- **Industry‑integrated capstones** with partner validation
- **Networking challenges** and structured industry engagement
- **Clubs & interest groups**: AI, Robotics, Startups, Policy, Creative Tech
- **Public demos** for projects & achievements
- **Mentor spotlights**, recognition ceremonies, milestone celebrations

---

### <a id="social"></a>6) Social

#### My Network (P2P)
- Build **peer‑to‑peer connections** across institutions & industries
- **Follow, connect, collaborate** with mentors, peers, professionals
- **Endorsements, peer feedback, recommendations**
- **Study groups / project teams** with in‑platform comms

#### My Clubs
- Join/create **interest‑based clubs** (AI, Robotics, Startups, Policy, Creative Tech)
- Club‑specific **missions, events, challenges**
- **Curated resources & discussions**; faculty/industry mentorship

#### My Feed
- Personalized **updates on achievements, badges, scores**
- Notifications on **challenges, competitions, missions**
- **Content recommendations**: articles, videos, opportunities
- Social engagement: **likes, comments, shares**

#### My Events
- Discover/register for **competitions, hackathons, webinars, career fairs**
- **Reminders** for upcoming events
- Showcase **participation & outcomes** (certificates, badges)
- Access **post‑event insights**, networking, recordings

---

### <a id="alerts"></a>7) Alerts & Notifications

#### Alerts
- Milestones: **new badges, score updates, progression checkpoints**
- Upcoming **deadlines** for assignments, challenges, events
- **Verification status** updates (success/failure/unverified)
- **Industry updates**: new skills in demand, opportunities

#### Notifications
- **Career path** updates and AI recommendations
- **Peer activity**: achievements, leaderboard changes, collaboration requests
- **Event reminders**: webinars, competitions, club activities
- **Institution‑level** updates: policies, new courses, assessments
- **System**: onboarding steps, auth updates, retry actions

---

## <a id="nfrs"></a>Non‑Functional Requirements (NFRs)

| # | Category | Focus |
|---:|---|---|
| 1 | **Security & Compliance** | DPDP, APAAR, encryption, access control, audit trails |
| 2 | **Reliability & Availability** | Uptime SLA, graceful degradation, redundancy |
| 3 | **Business Continuity & DR** | RTO/RPO, tested backups/restores, multi‑region/zone failover, runbooks |
| 4 | **Performance & Scalability** | Low latency, India‑scale traffic, exam‑season spikes |
| 5 | **Data Management & Residency** | Quality, classification, storage within India, retention/deletion |
| 6 | **AI/ML Governance** | Accuracy, fairness (Indian demographics), explainability, rollback |
| 7 | **Architecture & Deployment** | Microservices, CI/CD, containers, infra‑as‑code |
| 8 | **Interoperability & APIs** | Versioned, standards‑based, idempotent |
| 9 | **Observability** | Monitoring, logging, alerting, auditability |
|10 | **Maintainability & Extensibility** | Configurable, modular, documented |
|11 | **Usability & Accessibility** | WCAG 2.1 AA, multilingual, intuitive UI |

---

## <a id="architecture"></a>Technical Architecture (High Level)

> **Note:** Diagrams are linked to the public repository images for quick reference.

### 1) System Context Architecture
![System Context](https://github.com/PratapBodimalla/pramaanik/blob/main/structurizr-Diagram1.png?raw=true)
![Legend](https://github.com/PratapBodimalla/pramaanik/blob/main/structurizr-Diagram1-key.png?raw=true)

### 2) Container Architecture
![Container](https://github.com/PratapBodimalla/pramaanik/blob/main/structurizr-Diagram2.png?raw=true)
![Legend](https://github.com/PratapBodimalla/pramaanik/blob/main/structurizr-Diagram2-key.png?raw=true)

### 3) API Component Architecture
![API Components](https://github.com/PratapBodimalla/pramaanik/blob/main/structurizr-Diagram3.png?raw=true)
![Legend](https://github.com/PratapBodimalla/pramaanik/blob/main/structurizr-Diagram3-key.png?raw=true)

---

### Quick Reference — 6E Dimensions
- **Education**  
- **Experience**  
- **Employability**  
- **Entrepreneurship**  
- **Extracurricular**  
- **Evidence**



