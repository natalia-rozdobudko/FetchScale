# FetchScale

FetchScale is a Java-based project using Cucumber, JUnit, and Selenium to automate the process of identifying the fake gold bar among nine bars using a balance scale. This project is part of an interview assessment.

## Table of Contents
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Packages and Files](#packages-and-files)
- [Challenge Solution](#challenge-solution)
- [Contributing](#contributing)

## Prerequisites
- **Java JDK 11** or higher
- **Maven**: Apache Maven 3.6.3 or higher


## Installation
1. **Clone the repository**:
    ```bash
    git clone https://github.com/natalia-rozdobudko/FetchScale.git
    cd FetchScale
    ```

2. **Build the project**:
    ```bash
    mvn clean install
    ```

3. **Run the tests**:
    ```bash
    mvn test
    ```

## Usage
1. **Open the website**: Go to [http://sdetchallenge.fetch.com/](http://sdetchallenge.fetch.com/).
2. **Run the automation script**: The Selenium script will interact with the website to find the fake gold bar.

## Packages and Files

### `src/test/java`

- **`com.fetchscale.pages`**: Contains Page Object Model (POM) classes for the web pages.
    - **`GamePage.java`**: Represents the balance scale game page and its elements.

- **`com.fetchscale.runners`**: Contains the test runners for Cucumber.
    - **`CucumberRunner.java`**: Configures and runs the Cucumber tests.

- **`com.fetchscale.step_definitions`**: Contains step definitions for Cucumber tests.
    - **`Hooks.java`**: Contains setup and teardown methods for the test scenarios.
    - **`ScaleStepDefs.java`**: Implements the steps for interacting with the balance scale.

- **`com.fetchscale.utilities`**: Contains utility classes used across the project.
    - **`BrowserUtils.java`**: Provides common browser-related utilities.
    - **`ConfigurationReader.java`**: Reads configuration properties from the `configuration.properties` file.
    - **`Driver.java`**: Manages WebDriver instances.

### `src/test/resources`

- **`features`**: Contains the Cucumber feature files.
    - **`Scale.feature`**: Defines the scenarios for finding the fake gold bar.

- **`configuration.properties`**: Contains configuration properties such as Browser and URL.

### `pom.xml`

- Maven configuration file managing the project dependencies and build process.

## Challenge Solution
### Problem Statement
Given a balance scale and 9 gold bars of the same size and look, find the fake gold bar that weighs less using the balance scale.

### Solution
1. **Divide and Weigh**: Divide the 9 bars into three groups of three.
2. **First Weighing**: Weigh two of the groups against each other.
    - If they balance, the fake bar is in the group not weighed.
    - If they don't balance, the lighter group contains the fake bar.
3. **Second Weighing**: Divide the lighter group into three individual bars and weigh two against each other.
    - If they balance, the remaining bar is the fake one.
    - If they don't balance, the lighter one is the fake bar.

### Implementation
The implementation is done using Selenium WebDriver to automate the weighing process on the provided website. The steps are defined in the Cucumber feature file and implemented in the step definition class.

## Contributing
1. **Fork the repository**.
2. **Create a new branch**: `git checkout -b feature/your-feature-name`.
3. **Commit your changes**: `git commit -m 'Add some feature'`.
4. **Push to the branch**: `git push origin feature/your-feature-name`.
5. **Open a pull request**.


