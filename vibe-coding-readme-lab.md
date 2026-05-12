# Vibe Coding Lab — README Builder (Fusion User Profile)

This lab helps you create a clear and practical `README.md` by first asking **numbered requirement questions**, then turning the confirmed answers into a usable project document.

---

## Lab Objective

Create a README for the **Fusion User Profile Web Application** that must satisfy these core requirements:

1. Support responsive design
2. Be usable on mobile devices
3. Use .NET 10 for backend and React for frontend, with **Atomic Design** on frontend
4. Include essential endpoints such as `/health`
5. Apply the **Repository Pattern**

---

## Recommended Workflow

### Step 1: Ask clarifying requirements as numbered questions

Ask short questions to lock down the README scope, for example:

- README language (Thai / English / bilingual)
- Project name
- Core MVP features
- Authentication requirement (yes/no)
- Data storage approach (e.g., in-memory)
- Health check style (`/health` only vs `live/ready` split)
- Deployment target (or local-first)
- Expected output files

> Goal of this step: reduce assumptions and make the README match the real requirement.

### Step 2: Summarize requirements for user confirmation

Provide a short summary such as:
- Project name
- Feature scope
- Constraints (e.g., no auth, in-memory, local-first)
- Technology structure

### Step 3: Create the first README draft

Recommended README structure:

1. Overview / Scope
2. Requirement Coverage (mapped to requirements 1–5)
3. Architecture Overview
4. Frontend Atomic Design Structure
5. Backend Repository Pattern Structure
6. API Endpoints (must include `/health`)
7. Acceptance Checklist

### Step 4: Review README quality

Review checklist:

- Covers all 5 core requirements
- Clearly states mobile + responsive behavior
- Clearly states .NET 10 + React + Atomic Design
- Clearly documents `/health` and its purpose
- Explains Repository Pattern in practical terms
- Uses clear and unambiguous language

### Step 5: Deliver final outputs

Minimum deliverables:

- A ready-to-use `README.md`
- A short summary of what was done and suggested next steps (if any)

### Step 6: Test the generated application

After vibe coding produces the application, verify it against the README requirements:

**Backend tests**

- [ ] `GET /health` returns HTTP `200` with a valid payload
- [ ] `GET /api/profile` returns the correct profile structure
- [ ] `PUT /api/profile/contact-links` updates contact links and reflects the change on the next GET
- [ ] `PUT /api/profile/visibility` updates visibility settings correctly
- [ ] Repository layer is decoupled — swapping `InMemoryUserProfileRepository` with a stub does not break the service layer

**Frontend tests**

- [ ] Profile page loads without errors on desktop (≥ 1024 px)
- [ ] Profile page is readable and usable at 375 px (mobile) and 768 px (tablet)
- [ ] No horizontal scroll appears on small viewports
- [ ] Touch targets (buttons, links) are large enough to tap comfortably
- [ ] Atomic Design hierarchy is intact: atoms → molecules → organisms → template → page

**Integration smoke test**

- [ ] Frontend calls the backend successfully in a local environment
- [ ] Profile data returned from the API is rendered correctly on the page
- [ ] No console errors appear in the browser during normal usage

> Tip: If any check fails, paste the failing test item back into Copilot Chat with the relevant code and ask for a fix. Keep it one issue at a time.

---

## Prompt Template (Copy-ready)

```text
Please create a README.md for a Fusion Solution user profile web application.
Before drafting, ask numbered clarifying questions first.
Then summarize the confirmed requirements and produce a README that includes:
1) responsive support
2) mobile-ready usability
3) .NET 10 backend + React frontend (Atomic Design)
4) essential endpoints such as /health
5) repository pattern

Keep the document practical, readable, and include an acceptance checklist at the end.
```

---

## Scope-Aligned Prompt (Based on your scenario)

```text
Create an MD lab for Vibe Coding with the following steps:

Create a README.md for a web application used as a user profile for Fusion Solution with these requirements:
1) support responsive design
2) usable on mobile
3) .NET 10 backend and React frontend, with Atomic Design for frontend
4) include essential endpoints such as /health
5) use repository pattern

Please review and produce README.md.
Before writing the README, ask numbered clarification questions in Copilot Chat (VS Code ask-question flow) for anything that is still missing.
```

---

## Testing Prompt (Copy-ready)

```text
The vibe coding for Fusion User Profile is complete.
Please run a post-coding review against the README requirements:

1. Verify that GET /health returns HTTP 200 with a valid response.
2. Verify that GET /api/profile returns the correct profile structure.
3. Confirm the Repository Pattern is properly applied — the service layer must not depend on a concrete data source.
4. Confirm the React component tree follows Atomic Design (atoms → molecules → organisms → template → page).
5. Check that the profile page is responsive at 375 px (mobile) and 1024 px (desktop) with no horizontal scroll.

For each item, state pass or fail. If any item fails, explain what is wrong and suggest the fix.
```

---

## Expected Outcome

By the end of this lab, you should have a README that is:

- Complete on technical requirements
- Ready to use as a baseline for implementation
- Easy to understand for both product and engineering teams
