https://github.com/mintira46/Prog2-Lecture-S25/releases

# Prog2 Lecture S25 — Java, Testing, Clean Code, Refactoring

[![Releases](https://img.shields.io/badge/Releases-download-blue?logo=github)](https://github.com/mintira46/Prog2-Lecture-S25/releases) ![Java](https://raw.githubusercontent.com/github/explore/main/topics/java/java.png) ![Testing](https://raw.githubusercontent.com/github/explore/main/topics/testing/testing.png) ![Clean Code](https://raw.githubusercontent.com/github/explore/main/topics/refactoring/refactoring.png)

Welcome to the course materials for "Programmieren 2" (Summer 2025). This repository collects lecture slides, lab exercises, examples, and sample solutions. It targets students, instructors, and self-learners who want to improve Java skills, testing practice, refactoring techniques, logging, and clean code habits.

Table of contents
- About this repo
- Learning goals
- Topics and tags
- How the course is organized
- Lecture notes and slides
- Labs and exercises
- Assignments and grading
- Development environment
- How to build and run code
- Running tests and coverage
- Logging and diagnostics
- Clean code and refactoring guidelines
- Git workflow and collaboration
- Releases and downloadable artifacts
- Contributing
- Resources and references
- License and contact

About this repo
- Repo name: Prog2-Lecture-S25
- Course: Programmieren 2 (Summer 2025)
- Focus: Java programming, unit testing, refactoring, logging, clean code, teaching resources
- Topics/tags: clean-code, git, hacktoberfest, java, logging, oer, open-educational-resources, programming, refactoring, teaching-materials, teaching-website, testing

Learning goals
- Write clear Java code that one can read and modify.
- Design unit tests that catch bugs and document behavior.
- Apply refactoring rules to improve structure without changing behavior.
- Use logging to diagnose runtime issues.
- Use Git to track changes and collaborate.
- Build small systems that use dependency injection and modular design.
- Master testing tools such as JUnit and assertion libraries.
- Apply continuous integration to run tests on push.

Course audience
- Students with basic programming knowledge in Java.
- Developers who want to improve test-driven habits.
- Lecturers who need ready-to-use slides and exercises.
- Self-learners who want structured materials.

How the course is organized
- Lectures: 12 main lectures. Each lecture has slides and a short summary.
- Labs: Weekly lab assignments with guided tasks and test suites.
- Exercises: Micro-challenges to practice single concepts.
- Projects: Two small projects that combine the topics into working apps.
- Office hours: Weekly live sessions and recorded answers.
- Grading: Labs count 40%, projects 50%, participation 10%.

Lecture notes and slides
- Slides include code samples, diagrams, and exercises.
- Formats: PDF for slides, Markdown for notes, and ZIP for source code.
- Each lecture folder contains:
  - slides.pdf
  - notes.md
  - examples/ (runnable projects)
  - lab/ (assigned tasks)
- Use the slides in class or for self-study. The slides contain code snippets that you can copy and run.

Lecture index (short)
1. Java basics recap and modern features (records, var, streams)
2. Object-oriented design and SOLID
3. Collections, generics, and functional patterns
4. Exceptions and defensive programming
5. Unit testing with JUnit 5
6. Test doubles and mocking
7. Logging, diagnostics, and structured logs
8. Refactoring patterns and smells
9. Design patterns in practice
10. Build tools and dependency management (Maven or Gradle)
11. Continuous integration and test automation
12. Final project walkthrough and deployment

Labs and exercises
- Labs include a scoring script that runs tests and reports feedback.
- Each lab includes a baseline project and a full test suite.
- Labs aim at small increments. Each lab lists learning outcomes and tasks.
- Typical lab steps:
  1. Clone the repo or download the lab package.
  2. Read the task in lab/README.md.
  3. Implement the required methods.
  4. Run the tests.
  5. Submit via Git or the learning platform.
- The tests show failing cases and expected behavior. Use tests as documentation.

Assignments and grading
- Labs: Submit code in your personal fork or via the course platform.
- Projects: Push to a GitHub repository and open a pull request against the course organization if required.
- Grading rubric:
  - Correctness: 60%
  - Tests: 20%
  - Code quality: 10%
  - Documentation and README: 10%
- Use tests to validate correctness. Provide clear commit messages and incremental commits.

Development environment
- Java 17 or newer
- JDK vendor: AdoptOpenJDK, Eclipse Temurin, OpenJDK are fine.
- Build system: Maven 3.8+ or Gradle 7+
- IDE: IntelliJ IDEA, VS Code, or Eclipse
- Test framework: JUnit 5
- Mocking: Mockito or similar
- Static analysis: SpotBugs, Checkstyle, or Error Prone (optional)
- Logging: SLF4J with Logback

Recommended setup
- Install JDK 17
- Install Maven or Gradle
- Configure your IDE to use the JDK and import the project
- Enable annotation processing if you use Lombok
- Run mvn test or ./gradlew test to run test suites

How to build and run code
- With Maven:
  - mvn clean install
  - mvn -DskipTests=false test
  - mvn -q exec:java -Dexec.mainClass="com.example.Main"
- With Gradle:
  - ./gradlew clean build
  - ./gradlew test
  - ./gradlew run --no-daemon
- Sample run steps:
  1. Open a terminal.
  2. cd to the example project folder.
  3. mvn clean test
  4. mvn exec:java -Dexec.mainClass="com.example.Main"
- The example projects include README.md with exact commands.

Running tests and coverage
- Unit tests use JUnit 5.
- Run all tests with mvn test or ./gradlew test.
- Use coverage tools:
  - JaCoCo for code coverage.
  - Report generation:
    - mvn jacoco:report
    - ./gradlew jacocoTestReport
- CI will fail the build if coverage drops below the set threshold.
- Test structure:
  - Unit tests live under src/test/java.
  - Integration tests live under src/integrationTest/java or a separate module.
  - Keep tests fast and deterministic.
- Test naming:
  - Use descriptive test names.
  - Use given_when_then style or methodName_condition_expected.

Logging and diagnostics
- Use SLF4J as facade and Logback as backend.
- Configure logging via logback.xml in resources.
- Keep log levels:
  - ERROR for failures that require action.
  - WARN for potential issues.
  - INFO for key lifecycle events.
  - DEBUG for internal state during development.
  - TRACE for deep troubleshooting.
- Avoid logging sensitive data.
- Use structured logging where possible. Attach context via MDC for request id or user id.
- Tips:
  - Log at the right level.
  - Log exceptions with stack traces.
  - Include minimal context that helps debug.
- Example:
  - logger.info("User {} logged in from {}", userId, ipAddress);

Clean code and refactoring guidelines
- Keep methods short and focused.
- Name variables and methods clearly.
- Use immutability where it makes sense.
- Break classes that do too much.
- Favor composition over inheritance.
- Apply refactoring techniques:
  - Extract method to reduce complexity.
  - Rename for clarity.
  - Introduce parameter object when you have many parameters.
  - Replace type code with subclasses or enums.
  - Move method to the class that owns the data.
- Use automated tests to protect behavior while refactoring.
- Avoid premature optimization.
- Prefer readable code over clever code.

Refactoring exercises included
- Small refactor tasks tagged by difficulty: easy, medium, hard.
- Each task includes:
  - A codebase with a failing or brittle test.
  - Hints and an expected shape after refactor.
  - Tests that ensure no behavior change.
- Sample tasks:
  - Extract a long switch into polymorphism.
  - Remove duplicated code across modules.
  - Replace boolean flags with strategy pattern.

Git workflow and collaboration
- Use a small-team friendly workflow.
- Branching model:
  - main (stable)
  - develop (integration)
  - feature/* for new features
  - fix/* for bug fixes
  - release/* for release prep
- Commit messages:
  - Use present tense: "Add test for user validation"
  - Keep messages short and descriptive.
  - Use conventional commits if you want automated changelogs.
- Pull requests:
  - Use PR description for rationale.
  - Link to related issues.
  - Run tests in CI before merging.
  - Request at least one review.
- Merge strategy:
  - Use squash merges or merges that preserve history based on team preference.
- Rebase local work to keep history tidy when appropriate.

CI and automation
- Use GitHub Actions for CI.
- Typical workflow:
  - On push or PR, run: mvn -DskipTests=false test, static analysis, jacoco, and build.
  - Run on matrix to support multiple JDK versions if needed.
- Example workflow steps:
  - Checkout
  - Set up JDK
  - Cache Maven/Gradle
  - Run tests
  - Publish coverage report
- Badges:
  - Add build and coverage badges to README.

Coding standards
- Use 4 spaces for indentation or follow the team style.
- Limit line length to 100 chars.
- Place braces consistently.
- Use final for fields that do not change.
- Favor Optional over null where it improves clarity.
- Document public APIs with Javadoc.
- Keep module boundaries explicit.

Example structure of a lecture project
- /lecture-01-java-modern
  - slides.pdf
  - notes.md
  - examples/
    - src/main/java/...
    - src/test/java/...
  - lab/
    - task.md
    - starter-code.zip
    - tests.zip

Sample code snippet (Java)
```java
public class Calculator {
    private final Logger logger = LoggerFactory.getLogger(Calculator.class);

    public int add(int a, int b) {
        logger.debug("add({}, {})", a, b);
        return a + b;
    }
}
```
Use tests to lock behavior:
```java
@Test
void addTwoNumbers() {
    var calc = new Calculator();
    assertEquals(5, calc.add(2, 3));
}
```

Releases and downloadable artifacts
- You can find packaged materials and ready-to-run artifacts on the Releases page.
- The Releases page hosts ZIP files, example jars, and launcher scripts.
- Download the release asset and execute the included script or jar to run examples.
- For this repository, download the file(s) from:
  https://github.com/mintira46/Prog2-Lecture-S25/releases
- After you download a release archive, extract it and run the provided launcher:
  - On Linux/macOS: ./run-example.sh
  - On Windows: run-example.bat
  - Or run the JAR: java -jar prog2-lecture-s25-examples.jar
- The release artifacts include:
  - slides.zip: All PDF slides per lecture.
  - labs.zip: All lab starter code and tests.
  - examples.jar: Runnable examples used in lectures.
- Use the release assets as a quick start if you do not want to clone the full repository.
- If a download does not work, check the Releases section on the repository page for the latest artifacts.

Project examples and demos
- Demo apps show unit testing, logging, and refactoring patterns.
- Demos include:
  - Todo app with tests and a simple CLI.
  - Calculator with property-based tests.
  - File processor that demonstrates logging and error handling.
- Each demo contains:
  - README with run commands
  - Tests and expected inputs
  - A small CI configuration

Teaching materials and open educational resources (OER)
- Slides and notes use an open license to allow reuse and adaptation.
- Lecture content includes:
  - Learning objectives per slide
  - Classroom exercises with hints
  - Instructor notes with timing and expected outcomes
- Reuse:
  - You may reuse slides and labs for your own course if you follow the license.

Assessment and feedback
- Automated tests give immediate feedback.
- Instructors may provide manual review for code quality and design.
- Peer review:
  - Pair students for code review sessions.
  - Use a checklist: readability, tests, design, logging.
- Feedback items:
  - Test coverage gaps.
  - Design improvement suggestions.
  - Performance hotspots if relevant.

Security and privacy
- Do not commit secrets into the repository.
- Use .gitignore to keep IDE settings and local files out.
- Use environment variables or a secrets manager for CI tokens.

Contributing
- We welcome pull requests that fix issues, add exercises, or improve notes.
- Contribution steps:
  1. Fork the repo.
  2. Create a branch feature/your-change.
  3. Implement changes and add tests.
  4. Run the full test suite.
  5. Open a pull request with a clear description.
- Tag contributions with the appropriate topic, such as hacktoberfest if eligible.
- Maintain clear commit history. Keep commits focused and atomic.

Issue tracking
- Open issues for:
  - Bugs in the materials.
  - Typo fixes.
  - New exercise suggestions.
  - Request for additional examples.
- Use labels to categorize issues: bug, enhancement, doc, question.

Images and visual assets
- Icons in this README use GitHub Explore images for topics.
- Use SVGs for diagrams when you want crisp rendering.
- Include sequence diagrams for important patterns.
- Include UML or plantuml diagrams for class relationships.

Teaching website integration
- The materials work as a backend for a static teaching website.
- Convert Markdown to a site using a static site generator:
  - Jekyll, Hugo, or MkDocs
- Provide a site that lists lectures, labs, and schedules.
- Use the slides distribution to host PDFs on the site.

Examples of common student tasks
- Implement a missing method and run tests.
- Find and fix a bug using the test suite.
- Refactor a class to remove duplication.
- Improve logging to include request id.

Example task breakdown
- Task: Improve a text parser.
  - Step 1: Run tests to see failing cases.
  - Step 2: Add a new unit test for the reported case.
  - Step 3: Implement a small change to the parser.
  - Step 4: Run all tests.
  - Step 5: Refactor the parser to improve clarity.

Automated grading integration
- The test harness supports automated grading.
- Grading script will:
  - Run tests.
  - Report results in JSON.
  - Score based on passed test count and complexity.
- Integration with LMS:
  - Provide a zip artifact with instructions to import.

FAQ (short)
- Q: Which JDK should I use?
  - A: Use JDK 17 or newer.
- Q: Where are the slides?
  - A: Slides are in each lecture folder and in the Releases page. Download and execute the provided script from the releases if you prefer packaged assets.
- Q: How do I run labs on Windows?
  - A: Use the provided batch script in each lab archive or run the jar with java -jar.

Resources and references
- JUnit 5 user guide
- Mockito documentation
- Effective Java (book) for design tips
- Refactoring: Improving the Design of Existing Code (book)
- SLF4J and Logback documentation
- Official Java documentation and API references

Contact and maintainers
- Primary maintainer: course staff (listed in repository)
- Use GitHub issues for questions and bug reports.
- Use pull requests for content contributions.

License
- Materials use an open license for teaching resources. Check the LICENSE file in the repository for exact terms.

Appendix: quick commands cheat sheet
- Clone repo:
  - git clone https://github.com/mintira46/Prog2-Lecture-S25.git
- Build:
  - mvn clean install
  - ./gradlew build
- Run tests:
  - mvn test
  - ./gradlew test
- Run an example JAR:
  - java -jar examples/target/prog2-examples.jar
- Run a release launcher after download:
  - On macOS/Linux: ./run-example.sh
  - On Windows: run-example.bat

Download releases and run sample artifacts
- Visit the Releases page to find packaged slides, labs, and example artifacts:
  https://github.com/mintira46/Prog2-Lecture-S25/releases
- Download the ZIP or JAR asset you need.
- Unpack and run the launcher or execute the JAR as described earlier.

Badges and visibility
- Add badges from img.shields.io for:
  - Build status
  - Release download
  - License
  - Coverage
- Example:
  - [![Releases](https://img.shields.io/badge/Releases-download-blue?logo=github)](https://github.com/mintira46/Prog2-Lecture-S25/releases)

This README contains the course structure, workflows, and practical steps to use and extend the materials. Use the release artifacts to get a quick start, or clone the repository to work on specific lectures and labs.