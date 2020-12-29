# Architect ASP.NET Core applications

## Common design principles

1 Separatin of Concerns
2 Encapsulation
3 Dependency inversion
4 Explicit dependencies
5 Single responsibility
6 Don't repeat yourself(DRY)
7 Persistence ignorance
8 Bounded contexts

## Common web application architecture
1 N-Layer
- compile-time dependencies run from the top to the bottom

2 Clean Architecture (Onion Architecture)
- puts the business logic and application model at the center of the application
- infrastructure and implementation details depend on the Application Core

![clean architecture](..\images\Snipaste_2020-11-29_23-25-01.png)

2.1 the application's entities and interfaces are at the very center
2.2 just outside,but still in the Application Core, are domain services,which typically implement interfaces defined in the inner circle
2.3 outside of the Application Core,both the UI and the infrastructure layers depend on the Application Core,**but not on one another(necessarily)**

## Test
- Unit tests
A unit test runs **completely in memory and in process**.It doesn't communicate with the file system, the network, or a database. Unit tests should only test your code.









