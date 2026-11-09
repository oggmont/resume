# Info — Oscar Montero

Answers for behavioural and technical interview questions, plus a project log in STAR format (Situation, Task, Action, Result). Employer and client names are left out on purpose, as consultant work is usually under NDA. Describe clients by industry and size, never by name. Replace `[Company]` with the company you're interviewing with.

---

## Behavioural questions

### Tell me about yourself

I'm a software engineer specialised in test automation, with more than eight years of experience. I'm currently a Senior Software Developer in Test at a global IT consultancy in Wrocław, Poland.

I've worked on web, mobile and cloud projects in the automotive, financial, transportation, entertainment, e-commerce and journalism industries. On most of them I owned the quality process end to end. I've built test automation frameworks for Kubernetes infrastructure, backend APIs and web frontends, mainly in Java, JavaScript and Python.

I've worked onsite with teams in Mexico, Thailand, Vietnam, Spain and Poland. I have a technician degree in industrial electromechanics, a B.S. in Computer Science and Engineering, and I'm an ISTQB Certified Tester.

### What do you do? What does a normal day look like?

- Write and maintain tests in the automation framework.
- Review automation code from other testers and developers.
- Work with DevOps to run the automation inside the CI/CD pipelines.
- Review test cases in Jira and the project documentation.
- Create and update test documentation: test plans, strategies and test cases.
- Attend Scrum ceremonies: stand-up, sprint planning, review and retrospective.
- Run smoke and regression suites and report the results.
- Watch deployments and decide whether a regression run is needed.
- Read development documentation and update the test documentation to match.

### Strengths

- **Adaptability.** I'm comfortable in any kind of team. I've moved between many projects, clients, countries and workflows, and I've always settled in quickly.
- **Quick learner.** I know where to look for answers and how to learn a new technology on my own.
- **Easy to work with.** I care about the people I work with and keep communication open and friendly.
- **Problem solver.** I like breaking down a problem I don't yet understand until I find a way to test it.
- **I love coding.** I'm confident picking up new tools and languages, and I enjoy building frameworks, not only using them.

### Weaknesses

- **I sometimes take on more than I can handle.** I now estimate my tasks before I commit and tell the team early when my plate is full.
- **I avoid confrontation.** I'm working on raising disagreements early and backing them with data, which makes the conversation about facts, not people.
- **I lose interest in repetitive work.** I turn that into motivation to automate it: much of my best automation came from tasks I found boring.
- **I find it hard to ask for help.** I now set myself a time limit: if I'm stuck past it, I ask, because it saves the team time.

### What makes you a good candidate?

I have the skills to take on the responsibilities of this role at `[Company]`. I work well on my own and as part of a team. I've always found a way to adapt to new teams and projects, and I don't need much guidance to understand new technologies or concepts. I communicate clearly, and the people I've worked with have found me easy to work with.

### Where do you see yourself in five years?

- Having achieved meaningful goals for the company and for myself.
- Having built strong relationships with clients and colleagues.
- Holding more responsibility, possibly leading a small team.
- Influencing and supporting other engineers in their career paths.

---

## Experience questions

### Tell me about your experience

- At a software consultancy I worked on seven Agile projects from four offices: Guadalajara, Vietnam, Bangkok and Barcelona. On the last four of them I was the QA lead and owned all the QA processes.
- At a ride-sharing company I tested the iOS and Android apps for a car rental product.
- At a global IT consultancy I've spent three years on a vehicle-pairing platform for a major car manufacturer and a year and a half on a cloud landing zone for a large insurance company, where I'm technical lead of a team of 4+ testers.
- Overall I've worked in the automotive, financial, transportation, entertainment, e-commerce and journalism industries.
- I've automated both frontend and backend tests with Selenium-based tools, Cucumber, Robot Framework, TestCafé, Postman, JUnit, Rest Assured and Kyverno Chainsaw. I also run manual and exploratory testing where it makes more sense.
- On every project I wrote the QA documentation: test plan, strategy, test cases and reports.

### Concrete examples of products you've tested

| Product | What I tested |
|---|---|
| Cloud landing zone | Kubernetes cluster and CRDs, REST APIs |
| Car account pairing system | REST API and web app UI |
| Car rental app | iOS and Android apps |
| Video streaming encryption server | CLI and REST API |
| Stadium ticketing system | Web UI and GraphQL API |
| Journalism CMS | REST API and web UI |

### Tell me about one project: Stadium VIP suites exchange

- A web platform for a stadium to manage its VIP suites. Suite owners don't use their suite for every event (for example, if they only like basketball), so the app let them list it for a specific event and let other users rent it.
- **Owners** listed their suite for any event they chose.
- **Buyers** browsed suite photos and details, rented a suite and paid in the app.
- **Admins** managed users, events and suite information.
- **Architecture:** a Strapi CMS, a GraphQL layer over the CMS, a React web app for admins, owners and buyers, and GCP Cloud Functions for email notifications and scheduled jobs. It integrated a third-party ticketing provider for the venue's events and a third-party payment provider.
- We had about six months to deliver the whole system, and the requirements changed a lot along the way.

### What was the most challenging part?

I was the only QA for 10 developers, and several test items used technology I didn't know well:

- **Server-side rendering.** I asserted against the rendered HTML with a regex to confirm pages were rendered on the server.
- **GCP Cloud Functions** (mostly notifications). I built Postman tests that used an email REST API to verify that the emails were actually sent, covering the full integration.

To make it work, I prioritised the areas with the highest risk, such as payments and rendering, to get the most coverage out of my time. By the end we had a pipeline across three environments (dev, staging and prod) running smoke, regression and integration tests.

### A hard technical challenge you resolved

On the same stadium platform, I built a full validation pipeline covering the web UI, with its several user roles, and the GraphQL API behind it. All of it was in JavaScript: TestCafé for the frontend and Postman with Newman for the backend.

1. A pre-commit hook ran the unit tests locally.
2. After a push, smoke tests ran in the dev environment.
3. Merging to staging triggered the full regression suite.
4. After a green regression the code was merged to prod, where a final smoke test ran and posted the result to a Slack channel.

This gave us a high level of automation, smooth deployments and early bug detection, which mattered a lot for a platform that handles payments.

---

## Evidence of excellence

**Cut the encryption server load by over 50%.** A video streaming service in Australia needed a more efficient and secure encryption server. The plan was to encrypt 40–50% of each file. I tested files of many durations and sizes, measuring quality with the open-source VMAF tool, and showed that encrypting only 12% of a file was enough to make it unplayable in conventional media players. The client used these results to validate the new encryption servers.

**Built CI pipelines used by three development teams for over three years.** An automotive company needed pipelines to test the APIs behind their mobile app. I built the requested pipelines and added more: token authentication through an encryption process, vehicle-specific certificates, bug checks, status monitoring and standard regression, about 10 pipelines in total. They became part of the company's development process and stayed in use for over three years.

**Reduced test execution time from over 2 hours to 20 minutes.** A media and journalism company, whose systems were used by government agencies, needed a better testing process. I moved testing away from a deprecated UI and onto the API endpoints and the AWS Lambda functions that synchronised the databases and sent notifications. The faster suite changed their deployment process and gave developers continuous feedback.

---

## Project log

Average project length at the software consultancy: about 3.5 months (24 months across 7 projects).

### Cloud landing zone — insurance company (global IT consultancy · 1.5 years)

- **Situation:** A cloud landing zone for Azure and AWS, built on Kubernetes.
- **Task:** Validate the platform: automate the Kubernetes validations and test the platform's REST APIs, using Kyverno Chainsaw, PyTest with Tavern, and the Azure Portal and AWS Console.
- **Action:** Fully automated the tests for the main CRDs in Chainsaw, and automated the REST APIs that expose the platform's resources with PyTest and Tavern. They run every sprint in staging, and manually in prod.
- **Result:** A pipeline and process for testing Kubernetes CRDs and REST APIs and reporting the results.

### Vehicle pairing — car manufacturer (global IT consultancy · 3 years)

- **Situation:** Microservices for the enrollment service and a UI for the vehicle activation service, which pairs a user's app account with a vehicle.
- **Task:** Automate the APIs with test data for multiple vehicle generations and brands, and automate the main UI flows.
- **Action:** Built a full CI pipeline in Bamboo that runs Java automation (MrChecker, JUnit, Rest Assured, Selenium) and publishes results to Xray.
- **Result:** Pipelines producing results that several teams used to give the green light to large deployments.

### Car rental app — ride-sharing company (4 months)

- **Situation:** A car rental product with iOS and Android apps.
- **Task:** Run tests and develop automation for the mobile features.
- **Action:** Designed and executed test cases for new features and developed automation.
- **Result:** Steady improvement in test execution results over the engagement.

### Journalism data platform — media company (software consultancy · 8 months)

- **Situation:** A system that links existing journalism articles with person and corporation profiles created by its users.
- **Task:** Apply quality processes to a newly migrated API, build regression for the existing UI and check that every business rule was validated.
- **Action:** Built a full UI regression suite with a Selenium wrapper and an API test collection for the new API.
- **Result:** UI and API regression ran daily in Jenkins, with Slack notifications and ReportPortal reporting. It saved the time of the team that ran a manual sanity check on every two-week release.
- **Notes:** There was no system documentation, so I interviewed many people to collect the business rules. I owned my own continuous testing pipeline and learned a lot of CI/CD tooling.

### Trivia web app — TV channel (software consultancy · 2 months)

- **Situation:** A trivia web app for a well-known TV channel.
- **Task:** Apply quality processes across the development life cycle for the API and UI.
- **Action:** Built API test collections for the CMS and Lambdas, and tested the frontend and CMS manually.
- **Result:** Left a solid codebase for the team to continue. Covered the main paths, reported results and managed the relationship with the client.
- **Notes:** Testing exposed a problem with how the main video flow showed the answer options, and marketing redesigned the game rules.

### Stadium VIP suites exchange — sports venue (software consultancy · 5 months)

- **Situation:** A ticket sales platform for a stadium's VIP suites.
- **Task:** Test the CMS API, GraphQL API, GCP Cloud Functions and frontend UI.
- **Action:** Built test suites for the CMS and GraphQL APIs in Postman and for the UI in TestCafé, plus integration tests for the Cloud Functions.
- **Result:** Continuous testing from commit to prod: pre-commit and post-commit validation and regression in each environment. Strong user acceptance, and the first transaction was over $20,000 within 24 hours of launch.
- **Highlights:** Cloud Functions integration tests, the server-side rendering test, and the full validation pipeline.

### Video encryption — streaming technology company (software consultancy · 1.5 months)

- **Situation:** A new video codec to protect copyrighted content for a streaming service in Australia.
- **Task:** Apply testing to the alpha version: the players and the encryption.
- **Action:** Joined for the last weeks. Built a test suite for the backend content management API and tested the iOS and Android players manually with daily builds, since there was no CI/CD. Tested the encryption server integration and pushed for more unit tests.
- **Result:** Full app testing, an API test suite and integration testing of the encryption process.
- **Bug found:** Boundary testing showed that short videos sometimes crashed before the end, because the last block's length wasn't checked. It didn't reproduce every time because the encryption was random.
- **Experiment:** Used the open-source VMAF tool (Python) to find the minimum encryption percentage that makes a video unusable (see Evidence of excellence).

### Wallet credit feature — fintech company (software consultancy · 4 months)

- **Situation:** A new feature in a wallet app, integrating with a local bank and a supermarket.
- **Task:** Own backend and frontend automation (QA team of 4, 15+ developers).
- **Action:** Built full backend and frontend regression in Robot Framework.
- **Result:** Covered the most important cases following best practices, running in a Jenkins job on every commit.
- **Highlights:** Owned automation for both backend and frontend. Refactored the whole codebase to follow Gherkin and Robot best practices. When the pipeline kept breaking, improved communication with the team to avoid conflicts.

### Wallet payments feature — telecommunications company (software consultancy · 2 months)

- **Situation:** A new feature in a telecommunications web app that used its own wallet system for payments.
- **Task:** Own all API tests (QA team of 3, 5+ developers).
- **Action:** Built full API regression in Robot Framework (Python).
- **Result:** Complete coverage of happy and negative paths, running in a Jenkins job on every commit.
- **Notes:** Onsite with a different company and culture.

### Reference website — documentary company (software consultancy · 1.5 months)

- **Situation:** A single-page web application for a well-known documentary company that needed extra QA help.
- **Task:** Increase API integration coverage and add visual validation tests for the main page (QA team of 2 plus a client QA manager, 7+ developers).
- **Action:** Wrote API tests in JavaScript and introduced visual validation testing with Applitools Eyes.
- **Result:** Visual validation tests running in a CircleCI pipeline.
