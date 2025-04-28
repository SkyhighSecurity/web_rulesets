This folder contains the source code for the automated unit tests used to verify rule functionality. 

To build:

dotnet build solutionName.sln

To run the tests:

dotnet test solutionName.sln --no-build --logger:nunit
