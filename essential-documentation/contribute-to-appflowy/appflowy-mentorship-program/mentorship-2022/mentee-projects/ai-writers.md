---
description: Yatendra Kumar
---

# AI Writers

### Problem

Writing can often be time-consuming, tiring, and occasionally frustrating. Whether it's composing an email, jotting down a to-do list, or drafting a blog post, the challenge lies in the mental effort required to organize thoughts and ideas coherently. Moreover, prevalent issues like writer's block can compound these difficulties. There is a clear need for intelligent tools that can assist in generating and organizing content efficiently.

***

### Solution

AI-powered writing assistant using Flutter and the GPT-4 model from OpenAI. The assistant, tentatively named "AI Writers", will assist users in generating and organizing content efficiently. This includes automatic to-do list generation, blog post drafting, and outline creation.

Similar to the notion AI, we can keep a button or just press space for "ask AI" ![Screenshot 2023-06-12 at 2 25 55 PM](https://github.com/AppFlowy-IO/AppFlowy/assets/62821607/5f12c9df-c18d-4b72-9658-925622ae24a1)

***

### Goals

The successful completion of this project will involve:

* A fully functional API wrapper using Rust that uses AI to generate to-do lists, create outlines, and draft blog posts.
* A user-friendly interface that encourages engagement and facilitates ease of use.
* Comprehensive documentation covering the architecture of the application, functionality, usage instructions, and the integration process of the GPT-4 model.
* A well-structured thoroughly commented codebase for easy understanding and future development.

***

### Implementation Design

* The application will be developed using Rust & Flutter, which allows for cross-platform compatibility.&#x20;
* OpenAI's GPT-4 model will provide AI-powered writing assistance.&#x20;
* Rust will be used for network requests to the OpenAI API.

***

### Timeline:

**Week 1 (19/06/2023):**

Tasks:

* [x] Research and Understand GPT-4
* [x] Understand appflowy coding practices.
* [x] Research if there are existing Rust libraries that wrap GPT-4

Milestones:

1. Gain a comprehensive understanding of GPT-4 capabilities and functionalities
2. Gain in depth understanding of appflowy best coding practices integrated in CI/CD.
3. Determine if there are existing Rust libraries available for GPT-4 integration

**Week 2 (26/06/2023):**

Tasks:

* [x] Develop first working version of Rust wrapper for OpenAI API
* [x] Initiate exploration of AppFlowy backend system

Milestones:

4\. Develop a basic Rust wrapper for OpenAI API with minimal functionality.

5\. Understand the basic structure and components of the AppFlowy backend.

**Week 3 (03/07/2023):**

Tasks:

* [x] Gain deeper understanding of Creating Systems with OpenAI API
* [x] Gain deeper understanding of prompt engineering to develop applications

Milestone:

5\. Build an end-to-end demo system using gpt-4 with proper prompting

**Week 4 (10/07/2023):**

Tasks:

* [x] Enhance Rust wrapper for OpenAI API with additional features
* [x] Delve deeper into the complexities of AppFlowy backend
* [x] Fix issue #2937 row banner overlay.

Milestones:

7\. Upgrade Rust wrapper for OpenAI API with advanced features.

8\. Gain a deep understanding of AppFlowy backend, including data flows and dependencies/

9\. Raise a PR for issue. (raised pr: #3009).

**Week 5 (17/07/2023):**

Tasks:

* [x] Finalize application design and user interface
* [x] Start integration of GPT-4 Rust Wrapper with backend
* [x] Complete the integration of GPT-4 Rust Wrapper with backend
* [x] Begin development of auto-generating to-do list feature

Milestones:

10\. Finalize application design and UI.

11\. Begin the process of integrating GPT-4 Rust Wrapper with rust backend structure.

12\. Successfully integrate GPT-4 Rust Wrapper with rust backend structure.

13\. Initiate the development of the to-do list feature.

**Week 6 (24/07/2023):**

Tasks:

* [x] Continue development of the to-do list feature
* [x] Start development of the outline creation feature

Milestones:

14\. Complete the development of the to-do list feature

15\. Initiate the development of the outline creation feature

***

### Midterm Valuation

* Gained comprehensive understanding of GPT-4 and AppFlowy's coding practices.
* Identified potential Rust libraries for GPT-4 integration.
* Developed a basic Rust wrapper for OpenAI API.
* Explored AppFlowy's backend structure.
* Built a demo system using GPT-4 with proper prompting.
* Enhanced Rust wrapper for OpenAI API with advanced features.
* Delved deeper into AppFlowy's backend complexities.
* Resolved a bug in AppFlowy (PR: #3009).
* Finalised application design and UI (similar to Notion AI).
* Initiated and completed GPT-4 Rust Wrapper integration with backend.
* Began development of auto-generating to-do list feature and completed it.
* Initiated development of outline creation feature.

***

**Week 7 (31/07/2023):**

Tasks:

* [x] Make Rust wrapper API code modular and scalable.
* [x] Write comprehensive tests for the API with 100% coverage.

Milestones:

16\. Achieve modular and scalable Rust wrapper API code.

17\. Completed tests for the API with 100% coverage.

**Week 8 (07/08/2023):**

Tasks:

* [ ] Build the frontend Flutter interface.
* [ ] Write thorough tests for the complete interface.
* [ ] Gain a clear understanding of the backend-to-frontend integration flow.

Milestones:&#x20;

18\. Completed and polished frontend Flutter interface.

19\. Full test coverage for the entire frontend interface.

20\. Deep understanding of the integration flow from backend to frontend.

**Week 9 (14/08/2023):**

Tasks:

* [ ] Address and resolve the Evernote importer issue (#2971).
* [ ] Integrate the Rust wrapper API with the Flutter frontend interface.
* [ ] Write comprehensive tests for the integrated system.

Milestones:&#x20;

21\. Successfully fixed the Evernote importer issue (#2971).&#x20;

22\. Successful integration of the Rust wrapper API with the Flutter frontend.&#x20;

23\. Completed tests for the integrated system.

**Week 10 (21/08/2023):**

Tasks:

* [ ] Test the complete project end-to-end to ensure seamless functionality.
* [ ] Address and fix any bugs or issues that may arise during testing.
* [ ] Begin migration of current OpenAI features on Flutter side to using Rust wrapper

Milestones:

24\. Complete the project documentation.

25\. Address and fix any bugs or issues that may arise during testing.

26\. Initiate the migration of current OpenAI features to using Rust wrapper.

**Week 11 (28/08/2023):**

Tasks:

* [ ] Finalize migration of current OpenAI features on Flutter side to using Rust wrapper
* [ ] Continue comprehensive testing and debugging of the application
* [ ] Resolve any remaining issues identified during final testing

Milestones: 27. Successfully migrate all current OpenAI features to use Rust wrapper 28. Continue comprehensive testing and debugging of the entire application 29. Ensure all identified issues are resolved and application is fully functional

**Week 12 (04/09/2023):**

Tasks:

* [ ] Finalize and review the entire project, ensuring all tasks are completed satisfactorily.
* [ ] Prepare the application for live deployment.
* [ ] Document the complete project in a detailed blog, covering architecture, development process, and usage instructions.

Milestones:&#x20;

30\. Successful project review and preparation for final live deployment.&#x20;

31\. Successfully prepare the application for deployment, with all features working as expected&#x20;

32\. Completion of a comprehensive blog documenting the entire project.

***

### Impact

The successful implementation of this project will provide a powerful tool for users who require assistance with various writing tasks. By automating these tasks, users can focus more on their ideas and less on the mechanical aspects of writing.

Given the increasing demand for AI-powered tools and the widespread use of mobile devices, this project can potentially benefit a wide range of users.

***

### Risks and Mitigation

* **Risk:** Unfamiliarity with the GPT-4 model.
  * **Mitigation:** My recent completion of a course on prompt engineering from OpenAI gives me a solid foundation to understand and utilize the GPT-4 model effectively.
* **Risk:** API limitations, changes, or costs associated with using GPT-4.
  * **Mitigation:** For cost mitigation, the application will require the users to provide their API keys to access GPT-4, allowing the usage costs to be borne by the user directly.
* **Risk:** Time management due to other commitments.
  * **Mitigation:** Adherence to a strict schedule and prioritization of tasks will be key in managing this project alongside other responsibilities.
