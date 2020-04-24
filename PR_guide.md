
### Test
- check that test data is resembles one used in real life app
- check if test data payload can can be re-used (remove duplicated payload)
- Always double check that the test makes sense for what is tested for.
eg: if it needs a :before or :after action ensure that it is created and set properly
- are mocks used correctly? should stub/spies be used instead?
- Are fixtures repeated? can fixtures be generated/shared/centralized?


### variables
- check if variables have default values
- check variable naming
- check if object has required properties, if it should, and if these are tested
- check if variable are represented well in test to resemble real life scenario as much as they can (minimally)


### Design
- check how it ties into the exising design, if it should be designed better or not 
depending on what already exists
- Does there need to be any change in design or architecture documents
- 


### Structure
- check if the changes done in a file is where it should be done
- check that the code follows pattern already established in existing changes(functional, OOP, Factory etc)
- does the current organization of files make sense? can the team agree on file organization structure/pattern and follow through with it?


### configuration
- are the environment variables listed for different environments
- are the setup for build needed to be changed? for Travis or Circle CI?
- what images are you pulling for the build? should a lighter docker image be used instead?
- Do these configuration exist on the infrastructure? AWS or is Devops team setting it up?
- 


### promises
- check that promises are resolved the right way
- check that error is handled in promise appropriately



### Version Management
- check that version used is same for all configurations
- If it is new service or application, ensure it is using the lastest version available of 
the programming language or tool





## SDK


## Interfaces


## Classes


## functions

