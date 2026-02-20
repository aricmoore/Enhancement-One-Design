# Enhancement One: Software Design and Engineering

## **Introduction:**

The artifact selected for Enhancement One is `ItemManagementActivity.java` from my Inventory Application developed in CS 360: Mobile Architecture and Programming. The app as a whole acts as an inventory management solution that allows users to create, update, and track item quantities, and optionally receive SMS alerts for when items are out-of-stock. The original implementation of this class handled user input, database, updates, runtime permission checks, and SMS notifications within a single Android Activity.

I selected this artifact for the first enhancement because it represents a realistic, non-trivial mobile app component representing practical design challenges that developers commonly encounter in professional environments. While this artifact successfully met the functional requirements outlined in the assignment, it previously exhibited tightly-coupled responsibilities that limited scalability, readability, and maintainability. Therefore, this artifact was an ideal candidate for demonstrating software design and engineering best practices through refactoring.

## **Original Artifact:**

[Visit the Original Artifact (one file)](https://github.com/aricmoore/Enhancement-One-Design/tree/main/Original)

<details>
  <summary><strong>Enhancement Goal</strong></summary>

The goal of this enhancement was to improve separation of concerns by restructuring the Activity into a controller-style component responsible for coordinating user interaction, then delegating business logic and platform-specific duties to new, dedicated services.

</details>

## **Enhanced Artifact:**

[Visit the Enhanced Artifact (four files)](https://github.com/aricmoore/Enhancement-One-Design/tree/main/Enhanced)

<details>
  <summary><strong>Design and Implementation</strong></summary>

Inventory update logic was extracted into a new `InventoryService` class to isolate database interactions from the UI layer. A separate `SmsNotifactionService` was implemented to house SMS alert functionality including validating user preferences, checking runtime permissions, and sending notifications. Finally, permission logic was centralized into a reusable `PermissionManager` helper class to eliminate duplicated checks and improve security clarity. The newly-refactored `ItemManagementActivity` now focuses only on handling input, validating data, and orchestrating calls to the new services. This design proves to be more modular, maintainable, and aligned with industry best practices.

This refactoring introduces explicit service boundaries that enhance testability, maintainability, and potential for reuse across other components of the application. By isolating business logic from UI and platform-specific concerns, the design allows for easier unit testing of services without requiring Android framework dependencies. Additionally, employing a <i>controller-service-helper</i> architecture supports extensibility, such as adding logging, transaction handling, or new notification channels in the future with minimal impact to existing code.

</details>

<details>
  <summary><strong>Reflections / Lessons Learned</strong></summary>

Reflecting back on the enhancement, this process reinforced the importance of designing software beyond its immediate functionality; while the original implementation indeed worked as intended, the refactoring highlighted just how easy technical debt can accumulate when there is a failure to separate responsibilities. 

One key design challenge I faced was deciding how much logic should remain in the Activity versus being delegated to services, especially when considering Android’s framework constraints. This enhancement greatly strengthened my appreciation for <i>controller-based</i> design, service abstraction, and defensive programming. 

I believe that this enhancement demonstrated my ability to plan meaningful improvements and implement them in a manner that reflects current industry standards.

</details>

<details>
  <summary><strong>Course Outcomes</strong></summary>

This enhancement aligns with several course outcomes:
- **Outcome 1**: Refactoring the Activity to separate concerns required coordinating multiple components including UI, business logic, and SMS notification services, demonstrating collaboration across different application layers.
- **Outcome 2**: Detailed inline comments, class-level documentation, and the accompanying narrative showcase professional-quality written communication suitable for technical audiences.
- **Outcome 3**: The redesign applied <i>controller-service-helper</i> architecture, highlighting algorithmic and design trade-offs for modularity, maintainability, and scalability.
- **Outcome 4**: Implementation of reusable services, centralized permission management, and structured SMS notifications illustrates well-founded software engineering techniques that deliver value in a real-world mobile application.
- **Outcome 5**: Centralizing permission checks and securely handling SMS notifications reinforces a security-conscious approach to software design.

</details>

- ---

<i>Thanks for stopping by! Check out my two other enhancements below:</i>
- [Enhancement Two](https://github.com/aricmoore/Enhancement-Two-Design)
- [Enhancement Three](https://github.com/aricmoore/Enhancement-Three-Design)

<sub>© 2026 Arielle Moore. All rights reserved. | CS 499: Computer Science Capstone | View my [portfolio](https://aricmoore.github.io/) for more projects.</sub>
