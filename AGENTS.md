# AGENTS.md

## Project Overview
Build and maintain a **high-end professional services website** focused on:
- IT services
- Workflow automation
- Data engineering

Use this stack by default:
- **Frontend:** React + Tailwind CSS
- **Backend:** Supabase
- **Validation:** Zod for all user input (client and server boundaries)

## Non-Negotiable Standards
1. Use **functional React components only**.
2. Use **React hooks** for state/effects; avoid class components.
3. Use **Zod schemas for every form/input payload** before data is written or processed.
4. Keep UI **dark-mode-first**, with professional enterprise aesthetics.
5. After modifying any logic or implementation plan, always run:
   - `npm test`

## Site Execution Plan (Use Plan Mode First)
Before coding, enter plan mode in Codex:
- Action: `/plan`

Then use this planning prompt:

> I am building a high-end agency website for IT, automation, and data services. Create a detailed execution plan for a multi-page site including: (1) A hero section with a clear 'Book a Strategy Call' CTA. (2) Dedicated service landing pages for 'IT Infrastructure', 'Workflow Automations', and 'Data Engineering'. (3) A client lead intake form that sends data to a Supabase 'leads' table. Challenge my assumptions on the user journey for business clients.

## Outcome-First Feature Delivery
Implement features one-by-one using this framing:
- **Goal**
- **Context**
- **Inputs**
- **Constraints**
- **Output**

### Services Section Template Request
Use this example prompt pattern when building components:

> Goal: Build a responsive 'Services' section for the landing page. Context: React + Tailwind. Inputs: An array of objects containing service titles, descriptions, and hero icons. Constraints: Use a 3-column grid on desktop, 1-column on mobile. Ensure high accessibility (ARIA labels) and a professional dark-mode-first aesthetic. Output: A single component file ServicesSection.tsx with all necessary styles.

## Automation Skill Workflow
When asked to automate lead processing, use **$skill-creator** to create a skill named `lead-processor` that:
1. Scans Supabase `leads` every hour.
2. Identifies leads interested in "Automations".
3. Generates a customized 3-step automation proposal from lead inputs.
4. Logs drafts to a Supabase `proposals` table.

## Debugging Expectations
When debugging, require exact errors and test hypotheses explicitly.

Example debugging request format:

> Debug the lead intake form. Here is the exact stack trace: [Paste Error Here]. Analyze the hypothesis that the Zod schema is rejecting the phone number format, and refactor the validation to be more permissive for international business numbers.
