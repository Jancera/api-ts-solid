# API Structure

This API is based on SOLID principles using Typescript and Package by Feature approach.

## Creation flow

- **Entities**

  User entity (class for creating a user)

- **Repositories and Providers** 

  The repository has the methods related to the database, in this case, we have the findByEmail( ) and save( ).

  The provider has the methods related to the services that our application can perform, in this case, is only sendEmail( )

- **useCases**

  Here we have the use cases for our application, in this case, we have only the CreateUser use case, and here we have the CreateUserUseCase file that will receive our repository and our provider, together with the data and creating the user by the execute( ) function.
  The CreateUserController will generate the controller, receiving the Request from express, passing the data for the CreateUserUseCase execute( ) function, and waiting for the return to generate the Response.
  We also have the CreateUserDTO, DTO stands for Data Transfer Objects and is an interface that will determine the data structure for the execute( ) function on the CreateUserUseCase.
  
- **Controller** 

  In the end, we have the index.ts file that will mount everything, will create the Repositories and the Providers, pass it as an argument for our CreateUserUseCase and then pass the CreateUserUseCase for our Controller, which will be exported and used in our API routes.


