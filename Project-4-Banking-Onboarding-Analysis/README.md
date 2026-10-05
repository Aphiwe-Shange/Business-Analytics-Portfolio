# Project 4: Digital Account Onboarding - Systems Analysis and Agile Case Study

A business analysis case study that redesigns a retail bank's account-opening process, from a slow, branch-dependent journey to a digital self-service one. 

> **Scope Note:** This is a fictional cause study build to demonstrate business analysis skills. The bank, the baseline figures and the targets are illustrative assumptions (marked as such below), not data from a real institution.
>
> ---
>
> # 1. The business problem
>
> A mid-sized retail bank still opens most accounts in branches. The process depends on paper forms, certified document copies, manual re-typing and manual FICA/KYC checks.
>
> **Symptoms(assumed baseline for this cause study):**
>
> | Measure | As-Is (assumed) \ Why it hurts |
> |---|---|---|
> | Time from first visit to active account | 7-10 working days | Customers abandon or go to a competitor|
> | Applications abandoned before completion | ~35% | Lost revenue and wasted staff time | 
> | Applications needing rework (missing or unclear documents) | ~30% | Customers must return to the branch |
> | Data captured by hand into core banking | 100% | Typing errors and duplicated effort |
> | Cost to onboard one customer | High (staff time and 3 touchpoints) Poor unit economics |
>
> **Business Goal:** let a customer open an account on a phone in under 15 minutes, with exceptions handled by compliance staff instead of every case.
>
> ## 2. Approach
>
> This Project follows the analysis work that happens before developers write code in an Agile team:
>
> 1. Understand stakeholders and their needs
> 2. Model the current process (As-Is) and spot waste
> 3. Design the future process (To-Be)
> 4. Write requirements a user stories with acceptance criteria
> 5. Prioritize the backlog (MoSCow) and define an MVP
> 6. Sketch low-fidelity wireframes to confirm the experience with users and developers
> 7. Identify risks, assumptions and dependencies
>
> ## 3. Deliverables
>
> | Artefact | File |
> |---|---|
> | Stakeholder analysis | [documents/01-stakeholders.md](documents/01-stakeholders.md) |
> | Functional and non-functional requirements | [documents/02requrements.md](documents/02-requirements.md)
> | User stories with acceptance criteria | [docs/03-user-stories.md](docs/03-user-stories.md) |
> | Backlog prioritisation and MVP release plan | [documents/04-backlog-and-mvp.md](documents/04-backlog-and-mvp.md) |
> | Risks, assumptions and dependencies | [documentss/05-risks-assumptions.md](documents/05-risks-assumptions.md) |
> | As-Is process diagram | [diagrams/as_is_process.png](diagrams/as_is_process.png) |
> | To-Be process diagram | [diagrams/to_be_process.png](diagrams/to_be_process.png) |
> | Wireframes | [wireframes/onboarding_wireframes.png](wireframes/onboarding_wireframes.png) |
>
> ## 4. Process Models
>
> ### As-Is: Manual and branch-dependent
> ![As-Is process](diagrams/as_is_process.png)
>
> **Waste identifies:** double data capture (paper, then keyed in), manual document checking, a rework loop that sends the customer back to the branch, and a separate trip to collect the card.
>
> ### To-Be: digital with automated verification
> ![To-Be process](diagrams/to_be_process.png)
>
> **What changes:** customers capture their own data and documents, verification is automated through an identify-service API, and compliance analysts only see exceptions.
>
> ## 5. Wireframe
> ![Wireframes](wireframes/onboarding_wireframes.png)
>
> Four-step mobile flow: register, personal details, identity verification, review and sign.
> Progress is always visible and the customers can save and resume.
>
> ## 6. Targets (assumed) for the To-be process
>
> | Measure | Target |
> |---|---|
> | Tome to open an account | Under 15 minutes for straight-through cases |
> | Straight-through processing rate | 85% |
> | Exceptions resolved by compliance | Within 4 working hours |
> | Abondonment | below 15% |
>
> ## 7. Skills Demonstrated
>
> Stakeholders analysis, process modelling (As-Is / To-be), requirements elicitation, user stories and acceptance criteria (Given/When/Then), MoSCow prioritization, MVP definition, wireframing, risk analysis, regulatory awareness (FICA, POPIA) and Agile/SDLC thinking.
>
> ## Tools
>
> Graphvis (process diagrams), Python/Matplotlib (wireframes), Markdown (documentation). The same artefacts can be recreated in Draw.io, Lucidchart or Figma
