# Joke-Challenger-API-Clean-Archichecture

![device-2020-10-16-151849](https://user-images.githubusercontent.com/67366816/96268622-2e9bcf80-0fc1-11eb-9fdb-66dca8134896.png)
![device-2020-10-16-151913](https://user-images.githubusercontent.com/67366816/96268677-3d828200-0fc1-11eb-8a06-0c5cc96d50f8.png)
# Android Technical Test

## Objective

The goal of this simple exercise is for you to create an Android app which will consume content from the “The Internet Chuck Norris Database” API.

The documentation can be found at: http://www.icndb.com/api/ Display a list of jokes

The app should display a list of random jokes fetched from the API, filtered to remove explicit jokes.
For the purpose of this exercise you can ignore duplicate jokes.
Deliverables

We expect you to create an Android project that can be accessed by us via a version controlled repository (Github, Bitbucket, etc).

There is no stipulation for minimum deployment target, but should you wish to use the very latest platform technologies.

You are free to use whatever package manager and libraries are appropriate to complete the task.

If you are unsure how best to proceed during the course of the exercise you should use your own judgment to create what you think is the best solution. 

Part of this exercise is to see how you approach problem solving in the context of software development.

Evaluation criteria

We will take a look at the provided solution as a whole and consider:

● The quality/maintainability of the code delivered; quality is more important than a
complete solution

● The user experience

● How the details of the exercise were approached
Unit Tests


### Architecture pattern

![Clean-Architecture-graph-650x488](https://user-images.githubusercontent.com/67366816/96268772-5e4ad780-0fc1-11eb-929b-cb9f4b73e0d5.png)

To solve this challenger I have used clean archichecture implementation.

Clean architecture is a software design philosophy that separates the elements of a design into ring levels. The main rule of clean architecture is that code dependencies can only come from the outer levels inward. Code on the inner layers can have no knowledge of functions on the outer layers.

There are different opinions about how many layers Clean Architecture should have. The architecture doesn’t define exact layers but instead lays out the foundation. 
The idea is that you adapt the number of layers to your needs.

To keep things simple, you’ll use five layers:

Presentation: A layer that interacts with the UI.

Use cases: Sometimes called interactors. Defines actions the user can trigger.

Domain: Contains the business logic of the app.

Data: Abstract definition of all the data sources.

Remote: In our implementation is the more external layer it send request to the API.

![pat1](https://user-images.githubusercontent.com/67366816/96268416-f3999c00-0fc0-11eb-9691-96a0c593eff9.png)

## Project folder structure

presentation: An android module that represents the presentation layer.

domain: A java module without android dependencies.

data: An android module from where all the data is retrieved.

data-test: Tests for the data layer. Due to some limitations when using Robolectric I had to use it in a separate java module.

The benefits of clean code archichecture:

Independent of Database and Frameworks. The software is not dependent on an ORM or Database. You can change them easily.
Independence of UI. The UI can change easily, without changing the rest of the system and business rules.
Testable. Now it is intrinsically testable. You can test business rules without considering UI, Database, Mock servers, etc.

### Libraries used

Retrofit 
Retrofit is a type-safe REST client for Android, Java and Kotlin developed by Square. The library provides a powerful framework for authenticating and interacting with APIs and sending network requests.
This library makes downloading JSON or XML data from a web API fairly straightforward. Once the data is downloaded then it is parsed into a POJO which must be defined for each "resource" in the response.

RxJava2
RxJava is a Java VM implementation of Reactive Extensions: a library for composing asynchronous and event-based programs by using observable sequences.
It extends the observer pattern to support sequences of data/events and adds operators that allow you to compose sequences together declaratively while abstracting away concerns about things like low-level threading, 
synchronization, thread-safety and concurrent data structures.

koin
A pragmatic lightweight dependency injection framework for Kotlin developers.
Written in pure Kotlin, using functional resolution only: no proxy, no code generation, no reflection.

LeakCanary
LeakCanary’s knowledge of the internals of the Android Framework gives it a unique ability to narrow down the cause of each leak, helping developers dramatically reduce OutOfMemoryError crashes.


Testing

Junit4
JUnit is a simple framework to write repeatable tests. It is an instance of the xUnit architecture for unit testing frameworks. 

Mockito
Mockito is a popular mock framework which can be used in conjunction with JUnit. Mockito allows you to create and configure mock objects. 
Using Mockito greatly simplifies the development of tests for classes with external dependencies.

Espresso
Espresso used to test UI components
