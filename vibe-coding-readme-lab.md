# Vibe Coding Lab — README Builder for End Users

This lab helps you create a clear and practical `README.md` for the **Fusion User Profile Web Application** by chatting with Copilot step by step.

You do **not** need to write code. You only need to copy prompts, answer simple questions, and review the result.

---

## What You Will Create

By the end of this lab, you will have a ready-to-use `README.md` that explains:

1. The website works well on different screen sizes
2. The website is easy to use on mobile phones
3. The project uses:
   - .NET 10 for the system behind the website
   - React for the website screen
   - Atomic Design for organizing website parts
4. The project includes a basic system-check link such as `/health`
5. The project keeps data access separate from the main logic by using the Repository Pattern

> Do not worry if some terms sound technical. Copilot will help turn them into clear wording in the README.

---

## Recommended Workflow

### Step 1: Ask Copilot to start with questions

Copy this prompt into Copilot Chat:

```text
Please help me create a README.md for a Fusion Solution user profile web application.
Before writing the README, ask me short numbered questions first.
Use simple language because I am preparing this as an end-user lab.

The README must cover these requirements:
1. Responsive design
2. Mobile-friendly usage
3. .NET 10 backend and React frontend, with Atomic Design on the frontend
4. Essential endpoint such as /health
5. Repository Pattern
6. Use in-memory database for data storage (no external database required)
```

Copilot should ask questions similar to:

1. What language should the README use: Thai, English, or bilingual?
2. What is the project name?
3. What information should the user profile show?
4. Should this app have login now, or should login be skipped for the first version?
5. The first version should use an in-memory database (no external database required). Should this be noted as upgradeable to a real database later?
6. Should the project start as local-first, or should it mention future deployment?

---

### Step 2: Answer the questions simply

You can answer in short bullets. Example:

```text
1. English
2. Fusion User Profile
3. Name, job title, summary, skills, contact links, visibility settings
4. Skip login for the first version
5. Use sample data first, but allow database connection later
6. Local-first for now
```

If you do not know an answer, use these safe answers:

| If you are not sure about... | Answer this |
| --- | --- |
| Login | Skip login for the first version |
| Database | Use sample data first, then design it so a database can be added later |
| Deployment | Start local-first |
| Health check | Use a simple `/health` check |
| README language | Use English, or bilingual if the audience includes Thai users |
| Scope | Keep it as an MVP / first version |

---

### Step 3: Ask Copilot to summarize before writing

After answering, ask Copilot to confirm the plan first:

```text
Please summarize my confirmed requirements before writing the README.
Keep the summary short and show me what will be included.
Wait for my confirmation before creating the README.md.
```

Review the summary. If it looks correct, reply:

```text
Confirmed. Please create the README.md.
```

If something is wrong, reply with a short correction, for example:

```text
Please change the README language to bilingual Thai and English.
```

---

### Step 4: Review the README like an end user

After Copilot creates or drafts the README, check these items:

- [ ] The purpose of the profile website is clear
- [ ] It says the website should work on desktop, tablet, and mobile
- [ ] It says the mobile version should be easy to read and tap
- [ ] It mentions .NET 10, React, and Atomic Design
- [ ] It mentions `/health` as a basic system-check link
- [ ] It explains Repository Pattern in practical terms
- [ ] It includes a simple acceptance checklist
- [ ] It is understandable for both product and engineering readers

If the README feels too technical, ask:

```text
Please simplify the README wording for non-developer readers while keeping the required technical terms.
```

If the README feels too short, ask:

```text
Please add a little more detail to the overview, feature scope, and acceptance checklist.
```

If the README feels too long, ask:

```text
Please make the README shorter and easier to scan.
```

---

### Step 5: Ask Copilot to confirm the final output

Use this prompt at the end:

```text
Please confirm what you created, where the README.md was saved, and what my recommended next step is.
```

Expected answer from Copilot:

- The README was created or updated
- The file location is shown
- The next step is suggested clearly

---

## Copy-Ready Main Prompt

Use this if you want one single prompt to start the lab:

```text
Please create a README.md for a Fusion Solution user profile web application.
Before drafting, ask short numbered clarification questions first.
Use simple language so a non-developer can follow the process.

The README must include:
1. Responsive design support
2. Mobile-friendly usability
3. .NET 10 backend and React frontend, with Atomic Design on the frontend
4. Essential endpoint such as /health
5. Repository Pattern
6. Use in-memory database for data storage (no external database required)

After I answer, summarize the confirmed requirements and wait for my confirmation before creating the README.
The final README should be practical, readable, and include an acceptance checklist.
```

---

## Suggested README Sections

Ask Copilot to include these sections:

1. Project Overview
2. Who This App Is For
3. Main Features
4. Requirement Coverage
5. High-Level Architecture
6. Mobile and Responsive Behavior
7. API / System Check Summary
8. Data Access Approach
9. Acceptance Checklist
10. Future Improvements

---

## Expected Outcome

By the end of this lab, you should have:

- A clear `README.md` for the Fusion User Profile Web Application
- A short requirement summary confirmed by you
- A checklist showing how the README covers the required items
- A clear next-step recommendation from Copilot

---

## Success Checklist

Before finishing, confirm that:

- [ ] You answered Copilot's numbered questions
- [ ] Copilot summarized the requirements before writing
- [ ] You confirmed the summary
- [ ] The README covers all 5 required items
- [ ] The README is easy to read
- [ ] You know where the final `README.md` was saved
- [ ] You know the recommended next step

---

## Optional: Advanced Prompt for Building the App

Use this only after the README is final and you want Copilot to help create the actual application.

```text
Please implement the application as described in README.md.
Only ask me when you need a decision that is not covered in the README.
```

---

## Optional: Advanced Review Prompt After the App Exists

Use this only after the application has already been created.

```text
Please review the completed Fusion User Profile application against the README.
For each checklist item, mark Pass or Needs Fix.
If something needs fixing, explain it in simple language and suggest the next action.
```

---

## Notes for Facilitators

For workshops with non-developer participants:

- Keep the focus on the README, not implementation details
- Encourage short answers instead of perfect answers
- Ask Copilot to explain technical terms only when needed
- Do not require participants to run tests or inspect code
- Use the optional advanced prompts only for developer-focused sessions
