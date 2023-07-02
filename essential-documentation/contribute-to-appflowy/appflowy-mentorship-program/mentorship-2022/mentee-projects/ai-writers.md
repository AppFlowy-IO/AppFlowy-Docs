---
description: Yatendra Kumar
---


# AI Writers

## Problem:
Writing can often be time-consuming, tiring, and occasionally frustrating. Whether it's composing an email, jotting down a to-do list, or drafting a blog post, the challenge lies in the mental effort required to organize thoughts and ideas coherently. Moreover, prevalent issues like writer's block can compound these difficulties. There is a clear need for intelligent tools that can assist in generating and organizing content efficiently.

## Solution:
The proposed solution is an AI-powered Flutter application called "AI Writers," which will utilize the capabilities of GPT-4 from OpenAI to assist in a variety of writing tasks. The decision to use GPT-4 over GPT-3 or other models is rooted in its enhanced performance and ability to generate more nuanced and contextually relevant content. The app will include features such as automatic to-do list generation, blog post drafting, and outline creation, aiming to make the writing process more streamlined and efficient.

Similar to the notion AI, we can keep a button or just press space for "ask AI"
<img width="666" alt="Screenshot 2023-06-12 at 2 25 55 PM" src="https://github.com/AppFlowy-IO/AppFlowy/assets/62821607/5f12c9df-c18d-4b72-9658-925622ae24a1">

## Goals:
The successful completion of this project will involve:
- A fully functional API wrapper using Rust that uses AI to generate to-do lists, create outlines, and draft blog posts.
- A user-friendly interface that encourages engagement and facilitates ease of use.
- Comprehensive documentation covering the architecture of the application, functionality, usage instructions, and the integration process of the GPT-4 model.
- A well-structured thoroughly commented codebase for easy understanding and future development.

## Implementation Design:
The application will be developed using Rust & Flutter, which allows for cross-platform compatibility. OpenAI's GPT-4 model will provide AI-powered writing assistance. Rust will be used for network requests to the OpenAI API. The app will be developed in a modular manner for easy maintainability and expansion.

## Timeline:

**Week 1 (19/06/2023):**

Tasks:
- [ ] Research and Understand GPT-4
- [ ] Understand appflowy coding practices.
- [ ] Research if there are existing Rust libraries that wrap GPT-4

Milestones:

1. Gain a comprehensive understanding of GPT-4 capabilities and functionalities
2. Gain in depth understanding of appflowy best coding practices integrated in CI/CD.
3. Determine if there are existing Rust libraries available for GPT-4 integration

**Week 2 (26/06/2023):**

Tasks:
- [ ] Develop first working version of Rust wrapper for OpenAI API
- [ ] Initiate exploration of AppFlowy backend system

Milestones:

4. Develop a basic Rust wrapper for OpenAI API with minimal functionality
5. Understand basic structure and components of AppFlowy backend

**Week 3 (03/07/2023):**

Tasks:
- [ ] Enhance Rust wrapper for OpenAI API with additional features
- [ ] Delve deeper into the complexities of AppFlowy backend

Milestones:

6. Upgrade Rust wrapper for OpenAI API with advanced features
7. Gain a deep understanding of AppFlowy backend, including data flows and dependencies

**Week 4 (10/07/2023):**

Tasks:
- [ ] Finalize application design and user interface
- [ ] Start integration of GPT-4 Rust Wrapper with Flutter Interface

Milestones:

8. Finalize application design and UI
9. Begin the process of integrating GPT-4 Rust Wrapper with Flutter Interface

**Week 5 (17/07/2023):**

Tasks:
- [ ] Complete the integration of GPT-4 Rust Wrapper with Flutter Interface
- [ ] Begin development of auto-generating to-do list feature

Milestones:

10. Successfully integrate GPT-4 Rust Wrapper with Flutter Interface
11. Initiate the development of the to-do list feature

**Week 6 (24/07/2023):**

Tasks:
- [ ] Continue development of the to-do list feature
- [ ] Start development of the outline creation feature

Milestones:

12. Complete the development of the to-do list feature
13. Initiate the development of the outline creation feature

**Week 7 (31/07/2023):**

Tasks:
- [ ] Complete the development of the outline creation feature
- [ ] Begin development of the blog post drafting feature

Milestones:

14. Complete the development of the outline creation feature
15. Begin the development of the blog post drafting feature

**Week 8 (07/08/2023):**

Tasks:
- [ ] Complete the development of the blog post drafting feature
- [ ] Begin comprehensive testing and debugging of the application

Milestones:

16. Complete the development of the blog post drafting feature
17. Initiate comprehensive testing and debugging of the application

**Week 9 (14/08/2023):**

Tasks:
- [ ] Continue comprehensive testing and debugging of the application
- [ ] Begin documentation of the project

Milestones:

18. Identify and fix major bugs and issues in the application
19. Begin the documentation of the project, covering architecture, functionality, and usage instructions

**Week 10 (21/08/2023):**

Tasks:
- [ ] Complete documentation of the project
- [ ] Begin migration of current OpenAI features on Flutter side to using Rust wrapper

Milestones:

20. Complete the project documentation
21. Initiate the migration of current OpenAI features to using Rust wrapper

**Week 11 (28/08/2023):**

Tasks:
- [ ] Finalize migration of current OpenAI features on Flutter side to using Rust wrapper
- [ ] Begin the final round of comprehensive testing and debugging of the application

Milestones:

22. Successfully migrate all current OpenAI features to use Rust wrapper
23. Start final, comprehensive testing and debugging of the entire application

**Week 12 (04/09/2023):**

Tasks:
- [ ] Resolve any remaining issues identified during final testing
- [ ] Prepare the application for live deployment

Milestones:

24. Ensure all identified issues are resolved and application is fully functional
25. Successfully prepare the application for deployment, with all features working as expected


## Risks & Mitigation:

- **Risk:** Unfamiliarity with the GPT-4 model.
  - **Mitigation:** My recent completion of a course on prompt engineering from OpenAI gives me a solid foundation to understand and utilize the GPT-4 model effectively.

- **Risk:** API limitations, changes, or costs associated with using GPT-4.
  - **Mitigation:** For cost mitigation, the application will require the users to provide their API keys to access GPT-4, allowing the usage costs to be borne by the user directly.

- **Risk:** Time management due to other commitments.
  - **Mitigation:** Adherence to a strict schedule and prioritization of tasks will be key in managing this project alongside other responsibilities.
