# 0x03. Unittests and Integration Tests

## Project Overview

This project focuses on mastering unit testing and integration testing in Python, with a specific emphasis on testing utility functions, mocking, and working with external API interactions.

## Learning Objectives

By the end of this project, you will be able to:
- Understand the difference between unit and integration tests
- Implement parameterized tests
- Use mocking techniques effectively
- Test functions with external dependencies
- Apply testing best practices in Python

## Prerequisites

- Python 3.7
- unittest framework
- parameterized library
- mockup library

## Tasks Breakdown

### 0. Parameterize a Unit Test

**Objective**: Create unit tests for the `access_nested_map` function using parameterization.

**Key Requirements**:
- Inherit from `unittest.TestCase`
- Use `@parameterized.expand` decorator
- Test multiple input scenarios
- Verify function returns expected results

**Test Inputs**:
- `nested_map={"a": 1}, path=("a",)`
- `nested_map={"a": {"b": 2}}, path=("a",)`
- `nested_map={"a": {"b": 2}}, path=("a", "b")`

### 1. Parameterize Exception Test

**Objective**: Test exception handling for `access_nested_map` function.

**Key Requirements**:
- Use `assertRaises` context manager
- Test KeyError for invalid map accesses
- Verify exception messages
- Parameterize test inputs

**Test Inputs**:
- `nested_map={}, path=("a",)`
- `nested_map={"a": 1}, path=("a", "b")`

### 2. Mock HTTP Calls

**Objective**: Test `get_json` function without making actual HTTP requests.

**Key Requirements**:
- Use `unittest.mock.patch` to mock `requests.get`
- Verify method is called with correct URL
- Check JSON payload retrieval
- Parameterize test scenarios

**Test Scenarios**:
- `test_url="http://example.com", test_payload={"payload": True}`
- `test_url="http://holberton.io", test_payload={"payload": False}`

### 3. Memoization Testing

**Objective**: Validate the `memoize` decorator functionality.

**Key Requirements**:
- Create a test class with a method and memoized property
- Mock the original method
- Verify caching behavior
- Ensure method is called only once

### 4. GitHub Org Client - Organization Test

**Objective**: Test `GithubOrgClient.org` method.

**Key Requirements**:
- Use `@patch` decorator to mock `get_json`
- Parameterize with organization names
- Prevent external HTTP calls
- Verify correct method behavior

**Test Organizations**:
- `google`
- `abc`

### 5. Public Repos URL Property

**Objective**: Test `_public_repos_url` property generation.

**Key Requirements**:
- Use `patch` as context manager
- Mock `org` property
- Verify URL generation based on payload

### 6. Public Repos Retrieval

**Objective**: Comprehensive testing of `public_repos` method.

**Key Requirements**:
- Mock `get_json`
- Mock `_public_repos_url`
- Verify repository list retrieval
- Check method call counts

### 7. License Validation

**Objective**: Test `has_license` method functionality.

**Key Requirements**:
- Parameterize test inputs
- Verify license detection
- Test different repository configurations

**Test Scenarios**:
- Repositories with specific license keys
- Repositories without matching licenses

### 8. Integration Testing with Fixtures

**Objective**: Perform end-to-end integration testing of GitHub client.

**Key Requirements**:
- Use `@parameterized_class`
- Mock external requests
- Setup and teardown test fixtures
- Validate comprehensive client behavior

## Testing Commands

```bash
# Run all tests
$ python -m unittest discover tests

# Run specific test file
$ python -m unittest path/to/test_file.py
```

## Coding Standards

- Follow PEP 8 style guidelines
- Use type annotations
- Provide comprehensive documentation
- Ensure 100% test coverage

## Recommended Libraries

- `unittest`
- `unittest.mock`
- `parameterized`

## Potential Challenges

- Mocking external dependencies
- Handling complex nested structures
- Designing comprehensive test scenarios

## Best Practices

1. Always mock external services
2. Test both expected and edge cases
3. Keep tests independent
4. Use meaningful test names
5. Aim for high test coverage

## Contribution Guidelines

1. Fork the repository
2. Create a feature branch
3. Write tests before implementation
4. Ensure all tests pass
5. Submit a pull request

## License

This project is part of the ALX Backend Python curriculum.
