# Repository-Based System-Design Learning

A local-first learning product that helps intermediate developers study system design through public GitHub repositories.

## Language

**Learner**:
An intermediate developer using a repository-based course to prepare for system-design interviews.
_Avoid_: Student, user

**Repository-Based Course**:
An adaptive course that teaches system-design concepts through evidence in one checked-out public repository.
_Avoid_: Repo analysis, repository report

**Course Snapshot**:
The immutable repository commit that a Repository-Based Course analyzes and teaches.
_Avoid_: Repository version

**High-Level Design (HLD)**:
A course view of a repository's purpose, actors, system boundaries, major components, data flows, and deployment.
_Avoid_: Architecture overview

**Low-Level Design (LLD)**:
A course view of the internal structure and responsibilities of a selected component from the repository's High-Level Design.
_Avoid_: Detailed design

**Deep Dive**:
A Learner-selected Low-Level Design exploration of one component in addition to the course's automatically selected core components.
_Avoid_: Custom lesson

**Repository Evidence**:
A verifiable path or symbol in the checked-out repository that supports a course explanation or Tutor response.
_Avoid_: Source, proof

**HLD Diagram**:
An interactive representation of a High-Level Design whose elements are supported by Repository Evidence or identified as inferences.
_Avoid_: Architecture chart

**System-Design Review**:
The final course phase where a Learner consolidates the High-Level and Low-Level Design of the Course Snapshot.
_Avoid_: Final exam, capstone

**Interview Walkthrough**:
A Learner-written explanation of a Course Snapshot's design, including its HLD, a selected LLD component, trade-offs, and Repository Evidence.
_Avoid_: Final answer

**Tutor**:
An opt-in AI guide that explains repository evidence and supports the Learner without changing the Repository-Based Course or repository.
_Avoid_: Agent, assistant

**Personal Note**:
Learner-authored material associated with a Repository-Based Course and retained only on that Learner's device.
_Avoid_: Comment, annotation

**Lesson Version**:
A retained generated variation of a lesson for the same Course Snapshot, available until the Learner explicitly replaces it.
_Avoid_: Revision
