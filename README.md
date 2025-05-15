# API Automation Using Rest Assured & TestNG

This project provides a template for automating REST API testing across multiple environments using TestNG and the Rest Assured library.

[![Rest Assured Java API Automation CI](https://github.com/osandadeshan/rest-assured-java-api-automation-demo/actions/workflows/rest-assured-java-ci.yml/badge.svg?branch=master)](https://github.com/osandadeshan/rest-assured-java-api-automation-demo/actions/workflows/rest-assured-java-ci.yml)

## Prerequisites
1. Java
2. Maven
3. IntelliJ IDEA

## Project structure
src/
├── main/
│   └── java/
│       └── com/
│           └── api/
│               └── test/
│                   ├── configs/               # ConfigLoader, env readers (e.g., ConfigurationLoader.java)
│                   ├── constants/             # Global test constants (e.g., error codes, messages)
│                   ├── models/                # POJOs for Author, Book (Lombok-based model classes)
│                   ├── payloads/              # Test data generators (e.g., using JavaFaker)
│                   ├── repositories/          # Logic to load fake data or config-based test data
│                   ├── requests/              # API request classes using RestAssured
│                   └── utils/                 # Shared helpers (e.g., error verifiers, logging)
│
├── test/
│   └── java/
│       └── com/
│           └── api/
│               └── test/
│                   ├── tests/                 # TestNG test classes for AuthorTests, BooksTests, etc.
│
└── resources/
    ├── application-dev.properties             # Environment-specific config for dev
    ├── application-qa.properties              # Environment-specific config for QA
    ├── test-reporter.properties               # UI/format settings for Allure or ExtentReports
    ├── testng.xml                             # Full suite with Authors + Books
    ├── authors-suite.xml                      # Suite for only Author tests
    └── books-suite.xml                        # Suite for only Book tests

.github/
└── workflows/
    └── allure-report-github-actions.yml       # GitHub Actions to run tests + deploy Allure report



```

## ⚠️ Important: Steps to update the APIs
* Go to `com.restassured.example.util.RestClient`
* **Uncomment line 131** to enable your actual API functionality.
* Remove the **"TODO: "** comment, as it is no longer relevant

## How to run tests against different environments

mvn clean test -Denv=dev
mvn clean test -Denv=qa

2. Using Command Line
    * To run the smoke test suite against the UAT environment

      `mvn clean test 

    * To run the regression test suite against the QA environment

      `mvn clean test 

**Note**: By default, if no Maven profiles are selected, the tests will be executed on the `dev` environment.

## License
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/0b/License_icon-mit-2.svg/2000px-License_icon-mit-2.svg.png" alt="MIT License" width="100" height="100"/> [MIT License](https://opensource.org/licenses/MIT)

## Copyright
Copyright 2024 [MaxSoft](https://maxsoftlk.github.io/).
