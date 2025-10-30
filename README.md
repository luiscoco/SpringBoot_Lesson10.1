# SpringBoot_Lesson10.1

## Propmt for the Code Agent (Codex, Gemini Code Assistant or Copilot)

**Context**:

I am writing a data-layer test for a Spring Boot application using Spring Boot 3.3 and Java 17 (Maven project). 

The goal is to test a Spring Data JPA repository in a fast, isolated way.

**Task**:

Generate a JUnit 5 test for a TaskRepository interface.

**Constraints**:

The test must use the @DataJpaTest slice test annotation.

It should use the default in-memory H2 database configured by @DataJpaTest.

The test needs to inject and use the TestEntityManager to prepare data.

The repository being tested, TaskRepository, should also be injected.

Use AssertJ for assertions.

Do not use @SpringBootTest.

**Project specifics**:

Package: com.example.demo

Entity: Task with fields id (Long), description (String), and completed (boolean).

Repository: TaskRepository extends JpaRepository<Task, Long> with List<Task> findByCompleted(boolean completed).

**Steps**:

Assume a Task entity exists with id, description, and completed.

Assume TaskRepository extends JpaRepository<Task, Long> and has findByCompleted(boolean completed).

Generate TaskRepositoryTest.java under src/test/java/com/example/demo.

In the test method, use TestEntityManager to persist a new Task with completed = true.

Use TaskRepository to find tasks by completed = true via findByCompleted(true).

Assert that the retrieved list is not empty and contains a task with the expected description and completed = true.

Include the command to run the test.

**Deliverables**:

The full code for TaskRepositoryTest.java.

Confirmation that TaskRepository includes List<Task> findByCompleted(boolean completed) (no production change required).

The command to run the test.

**Acceptance Criteria**:

The test class has the @DataJpaTest annotation.

The test does not use @SpringBootTest.

The test uses TestEntityManager to set up the data.

The test uses the injected TaskRepository to execute the query.

The test successfully asserts the data integrity.

**Command to run**:

mvn -Dtest=TaskRepositoryTest test
