# Coding Practice Policy

## 1. Purpose
- To ensure code quality, maintainability, and consistency across all projects.
- To improve developer productivity and reduce development time.
- To minimize technical debt and future maintenance costs.
- To comply with industry best practices and security standards.
- To make sure that applications are secure and well tested before going to production.

### 1.2 Scope
- Applies to all software development projects within the company.
- Applies to all developers, regardless of their role or experience level.
- May exclude specific legacy systems or projects with unique requirements. [Find Exclusion List Below](#7-projects-excluded-from-this-policy)

## 2. Coding Standards

### 2.1 Code linting

Source code should have code linting enabled, to make sure that every developer has the same type of indentations, spaces, nestings & imports. This ensure that the code is redable and make the navigation easy for all the the teammates.

#### 2.1.1 NodeJS linting best practices

- Use of TypeScript across all projects.
- Use of Eslint for cleanup.
- use of prettier or editorconfig for clean indentations and spacings.

### 2.2 Naming Conventions:

Make sure to use meaningful names. Avoid using short abbrevations for names.

#### 2.2.1 NodeJS Naming Conventions

- All variables should be named in camelCase for both local and global scope. variables with constant values should be name in CAPITALCASE.
- funtions / class methods names should always be in camelcase.
- Class names should always be in PascalCase.
- for SQL base databases, column names in models use snake_case and for NoSQL based databases names should be in camelCase.
- Module name should always be in cameCase in this notatation `<moduleName>.<group>.<ext>`. example `adminUsers.controllers.ts`
  
### 2.3 Apply SOLID principle (Optional Recommended)
- **Single-responsibility Principle**: A class should have one and only one reason to change, meaning that a class should have only one job.

- **Open-closed Principle**: Objects or entities should be open for extension but closed for modification.

- **Liskov Substitution Principle**: This means that every subclass or derived class should be substitutable for their base or parent class.

- **Interface Segregation Principle**: A client should never be forced to implement an interface that it doesn’t use, or clients shouldn’t be forced to depend on methods they do not use.
- **Dependency Inversion Principle**: Entities must depend on abstractions, not on concretions. It states that the high-level module must not depend on the low-level module, but they should depend on abstractions.

### 2.4 Commenting
- Require comments for complex logic, non-obvious code, and design decisions.
- Use clear and concise comments.
- Avoid redundant comments.

### 2.5 Security

- Avoid putting secrets or other sensetive information / credentials on codebase.
- Make use of Environment Variables for credentials.
- Env file should never be upload over code repository.
- Make sure to frequently update libraries to avoid any security vulnerability (recommended to update quarterly).
- Make sure to check the size of library, number of downloads and last updated, before using a libary. 
- User inputs should be properly sanitized before going through actual business logic. use zod for nodejs projects.
- For development and testing use local or staging database.
- Make sure to remove logs, unwanted dependencies and test credentials before creating a pull request to production / staging.
- Make sure to disable debug mode on staging and production environment.
- Use proper error handling to avoid any crashes. A centralized error handling will be best suited.

## 3. Code Reviews

### 3.1 Process
- Create a PR for staging enviroment first.
- Label changes as Draft, Feature, Hotfix and Security.
- Make sure to name branch in this format `<label>/<developer_name>/<change_name or date>` e.g. `feature/aman_singh/create_user`.
- Make sure to dispose of the branch after merge.
- PR should be reviewed and approved by team / project lead, berfore merging to production.
- Changes made in the code should be clearly defined for review.
- Avoid added different changes all together in one pull request. 
- code should be build and properly tested locally before creating a PR.

## 4. Testing

### 4.1 Unit Testings
- Require unit tests for all critical code components business logic.

### 4.2 Integration Testing
- (Need a Discussion)
  
### 4.3 End To End Testing
- (Need a Discussion)

## 5. Version Control
- Code should contain a version in this format `major.minor.patch` e.g. `3.2.1`
- Before creating a release to production, a change log should be mainted.

## 6. Documentation

### 6.1 Code Documentation
- code containing business logic should have a clean documentation.
- API Documentation should be present within the source code, or link to the docuementation should be present withing the source code.
- For API documentation follow OpenAPI format.

> As a good practice create a mock API first that can be shared with fronted team to get their work started. 

#### 6.1.1 Tools
- Postman
- Swagger

#### 6.1.2 NodeJS Documentation
- make use of multiline comments everywhere.
- use JSDoc format to document functions.
Example Format
```ts
/**
 * Addition of two numbers
 * @param {a} number: First argument
 * @param {b} number: Second argument
 */
function addNumbers(a: number, b: number): number {
    return a + b
}
```
## 7. Projects Excluded from this policy

> None at the moment
