## Overview
Gradle is a versatile build automation tool that supports multi-language development. It is particularly popular for Java projects.

# Gradle Build Lifecycle

## Build Lifecycle
A Gradle build consists of three main phases:

![LifeCyclegradle](https://github.com/user-attachments/assets/fb407a41-12f1-4adc-91fe-86bfeade5c47)


1. **Initialization**
   - Gradle identifies which projects are involved in the build.
   - Creates a `Project` instance for each project.

2. **Configuration**
   - Evaluates the build scripts (`build.gradle` or `build.gradle.kts`) for all projects.
   - Constructs the task dependency graph.

3. **Execution**
   - Executes the tasks as per the task graph.
   - Tasks are executed in the order dictated by their dependencies.

## Example
Here is a simple example to illustrate the lifecycle phases:

```groovy
// settings.gradle
println 'Initialization phase'

// build.gradle
println 'Configuration phase'

tasks.register('exampleTask') {
    doFirst {
        println 'Execution phase - start'
    }
    doLast {
        println 'Execution phase - end'
    }
}

Running gradle exampleTask will produce the following output:

Initialization phase
Configuration phase
Execution phase - start
Execution phase - end
