# Java Source Code

This directory contains all Java implementation, source code, and solution artifacts following Maven/Gradle standards.

## Directory Structure

```
src/
├── main/
│   ├── java/                    # Production Java source code
│   │   └── com/
│   │       └── example/         # Root package (customize)
│   │           ├── models/      # Data models and entities
│   │           ├── services/    # Business logic
│   │           ├── controllers/ # API endpoints or request handlers
│   │           ├── utils/       # Utility functions
│   │           ├── config/      # Configuration classes
│   │           └── Main.java    # Application entry point
│   └── resources/               # Non-Java resources
│       ├── application.properties
│       ├── application.yml
│       ├── logback.xml          # Logging configuration
│       └── data/                # Data files, fixtures
│
└── test/
    ├── java/                    # Test source code
    │   └── com/
    │       └── example/
    │           ├── services/    # Service tests
    │           ├── controllers/ # Controller/API tests
    │           ├── utils/       # Utility tests
    │           └── integration/ # Integration tests
    └── resources/               # Test resources
        ├── application-test.properties
        └── test-data/
```

## Java Coding Standards

### Package Naming
- Use reverse domain notation: `com.company.project.module`
- Keep packages focused and organized
- Example: `com.example.learning.services`

### Class Organization
- One public class per file (with inner classes allowed)
- Clear naming: `UserService`, `UserController`, `UserRepository`
- Group related classes in packages

### Naming Conventions
- **Classes**: PascalCase (e.g., `UserService`)
- **Methods/Variables**: camelCase (e.g., `getUserById()`)
- **Constants**: UPPER_SNAKE_CASE (e.g., `MAX_USERS`)

### Documentation
```java
/**
 * Brief description of the class.
 * 
 * Longer description if needed, explaining purpose and usage.
 * 
 * @author Author Name
 * @version 1.0
 */
public class ExampleClass {
    
    /**
     * Description of the method.
     * 
     * @param param1 description of param1
     * @return description of return value
     * @throws ExceptionType when this condition occurs
     */
    public String methodName(String param1) {
        // implementation
    }
}
```

## Implementation Guidelines

1. **Separation of Concerns**: Keep business logic, data access, and presentation separate
2. **DRY Principle**: Avoid code duplication
3. **SOLID Principles**: Single Responsibility, Open/Closed, Liskov Substitution, Interface Segregation, Dependency Inversion
4. **Testing**: Write unit tests for all service/utility classes
5. **Exception Handling**: Use meaningful custom exceptions
6. **Immutability**: Prefer immutable objects where possible

## Testing Strategy

### Unit Tests
- Located in `src/test/java`
- Test individual methods and classes
- Use JUnit and Mockito
- Naming: `ClassNameTest.java` or `ClassNameTests.java`

### Integration Tests
- Located in `src/test/java/integration`
- Test interactions between components
- Use TestContainers for external dependencies
- Naming: `ClassNameIntegrationTest.java`

### Test Organization
```java
public class UserServiceTest {
    
    private UserService userService;
    private UserRepository mockRepository;
    
    @Before
    public void setUp() {
        // Initialize mocks
        mockRepository = mock(UserRepository.class);
        userService = new UserService(mockRepository);
    }
    
    @Test
    public void testGetUserById_WithValidId_ReturnsUser() {
        // Arrange
        // Act
        // Assert
    }
    
    @Test
    public void testGetUserById_WithInvalidId_ThrowsException() {
        // Arrange
        // Act
        // Assert
    }
}
```

## Build Configuration

### pom.xml (Maven)
- Declare dependencies
- Configure plugins
- Define build phases
- Set Java version (e.g., 11, 17, 21)

### build.gradle (Gradle)
- Similar to pom.xml but Groovy/Kotlin DSL
- More flexible and powerful

## Getting Started

1. Create your package structure under `src/main/java`
2. Implement core classes in appropriate subdirectories
3. Write unit tests alongside your code in `src/test/java`
4. Add configuration files in `src/main/resources`
5. Run and debug using your IDE or build tool
