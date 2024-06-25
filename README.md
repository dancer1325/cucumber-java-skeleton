# Cucumber-Java Skeleton
* Goal
  * how to install & run Cucumber!
    * **Note:** The simplest possible build script setup

## Cucumber features
* 1! feature file / 1! scenario / 3 steps -- Check 'belly.feature' --

## Use Maven
* 
  ```
  cd maven
  ./mvnw test
  ```  
  * Problems:
    * Problem1: "[ERROR]   The step 'I wait 1 hour' and 1 other step(s) are undefined."
      * Solution: Add the missing steps
  * Cucumber features -- are run via -- Cucumber's JUnit Platform Engine
  * `RunCucumberTest` class', `Suite` -- tells JUnit to -- kick off Cucumber

## Use Gradle
* 
   ```
  cd gradle
  ./gradlew test --rerun-tasks --info
   ```
    * Problems:
      * Problem1: "[ERROR]   The step 'I wait 1 hour' and 1 other step(s) are undefined."
        * Solution: Add the missing steps
    * Cucumber features -- are run via -- Cucumber's JUnit Platform Engine
    * `RunCucumberTest` class', `Suite` -- tells JUnit to -- kick off Cucumber


## Configuration 
* [cucumber-junit-platform-engine](https://github.com/cucumber/cucumber-jvm/tree/main/cucumber-junit-platform-engine)
  * [configuration parameters](https://github.com/dancer1325/cucumber-jvm/tree/main/cucumber-junit-platform-engine#configuration-options)
    * allow specifying
      * what features to run
      * where the glue code lives
      * what plugins to use 
    * if you use JUnit -> `@ConfigurationParameter` is the annotation to       configuration parameters are provided through the

### Run a subset of Features or Scenarios
* by *line*
  ```
  @SelectClasspathResource(value = "io/cucumber/skeleton/belly.feature", line = 3)
  ```

* by *tag*:
  ```
  @IncludeTags("zucchini")
  ```

## Running 1! scenario or feature
* Via
  * JUnit selectors
    * ⚠️ NOT (yet) supported by Maven and Gradle ⚠️
  * `cucumber.features` property
    * Recommendations: 👁️only execute the Cucumber engine 👁️
      * **Reason:** 🧠Cucumber ignores any other selectors from JUnit 🧠

### With Maven
* _Example:_ select the scenario on line 3 of the `belly.feature` file

```
./mvnw test -Dsurefire.includeJUnit5Engines=cucumber -Dcucumber.features=src/test/resources/io/cucumber/skeleton/belly.feature:3 
```
* If you want more detailed output during test execution ->  `-Dcucumber.plugin=pretty`

### With Gradle
* TODO: (I don't know how to do this. Feel free to send a pull request. ;))
