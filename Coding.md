1. The “Senior Engineer” Code Review
Prompt: “Act as a Senior Software Engineer specializing in Clean Code and SOLID principles. Review the code snippet below. Identify code smells, potential race conditions, or logic errors. Provide a refactored version of the code that improves readability and maintainability without changing the underlying functionality. Explain why you made each change.”

2. The “Legacy to Modern” Refactor
Prompt: “Act as a TypeScript Expert. Convert the following legacy JavaScript code block into modern TypeScript. Apply strict typing (avoid any), use Interfaces for object definitions, and implement modern ES6+ syntax (arrow functions, destructuring). Output the result as a single code block followed by a brief list of the types defined."

3. The “Instant Unit Test” Suite
Prompt: “Act as a QA Automation Engineer. Write a comprehensive unit test suite for the provided function using [Framework Name, e.g., Jest/PyTest]. Include test cases for the happy path, edge cases (null/undefined inputs), and potential error states. Ensure the tests follow the ‘Arrange-Act-Assert’ pattern.”

4. The “System Design” Architect
Prompt: “Act as a Cloud Solutions Architect. Design a high-level architecture for a [App Idea, e.g., Real-time Chat Application]. Outline the necessary components (Database, API Layer, Caching, Load Balancer) and recommend specific technologies for each (e.g., Redis, PostgreSQL, WebSocket). Create a text-based diagram (Mermaid.js format) showing the data flow between these components.”

5. The “Security Auditor”
Prompt: “Act as a Cybersecurity Analyst. Audit the following code block for OWASP Top 10 vulnerabilities (such as SQL Injection, XSS, or Insecure Deserialization). Point out the specific lines where vulnerabilities exist and rewrite the code to be secure. Explain the attack vector that the patch prevents.”

6. The “SQL Performance” Optimizer
Prompt: “Act as a Database Administrator. Analyze the following SQL query. Explain the likely execution plan and identify bottlenecks (e.g., full table scans). Rewrite the query for optimal performance, suggesting necessary Indexes that should be added to the schema. Prioritize execution speed.”

7. The “Design Pattern” Implementer
Prompt: “Act as a Lead Developer. Analyze this series of if/else statements. Refactor this logic by implementing the [Strategy Pattern / Factory Pattern] to make the code extensible and open for modification but closed for change (Open/Closed Principle). Provide the interface and the concrete class implementations."

8. The “Accessibility (a11y)” Fixer
Prompt: “Act as a Web Accessibility Expert. Review this HTML/React component. Identify elements that violate WCAG 2.1 guidelines (e.g., missing ARIA labels, poor contrast, keyboard navigation issues). Rewrite the markup to be fully accessible for screen readers. Add comments explaining the purpose of the specific ARIA attributes used.”

9. The “Algorithm Complexity” Explainer
Prompt: “Act as a Computer Science Professor. Analyze the Time and Space complexity (Big O Notation) of the algorithm below. Walk through the code line-by-line to explain how you calculated the complexity. Suggest an alternative algorithm or data structure that would improve the time complexity, if possible.”

10. The “Documentation” Generator (JSDoc/Swagger)
Prompt: “Act as a Technical Writer. Generate comprehensive documentation for this API endpoint code. Create an OpenAPI (Swagger) YAML definition that includes parameters, request body schema, and all possible response codes (200, 400, 500) with example payloads. Ensure the description is clear enough for a third-party developer to use.”
