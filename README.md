# Assignment 1 DevOps
Name: Heshan Mapa

Student Number: s3661741

## Stonk Inc
Stonk Inc faces several problems:
1. Application is built and deployed manually from the lead developer's laptop.
2. Bugs being introduced into prodcution which impacted revenue of Stonk Inc and reduced team morale with team members.

As the newly hired DevOps Practitioner, I proposed the following solutions:
1. Establishing a CI pipeline to automate builds and automate the testing processes.
2. Creating a version control system on github.

## Step-by-Step Solution
### Setting up a private repo in GitHub
First, we need to make a private repository on GitHub where we will work on the project. We will be ensuring we are using proper branching by using the GitHub Flow method, where all the new features we will be adding will be added and developed on feature branches and then merged into the main branch through the usage of Pull Requests which can then be later reviewed by the DevOp Practitioner (this case being me).

Screenshot of the GitHub Repo
![github repo](https://i.imgur.com/dUowg7H.png)

### Continuous Integration Building
We then have to set up integration between CircleCi and the GitHub repo.
![circleci](https://i.imgur.com/2CXMBYq.png)

## Testing in CircleCi
### 1. Unit Testing
Unit testing is a software testing method where individual units of the source code are tested to determine if there have been any issues made by the developer. I have integrated Unit Testing within CircleCi so whenever we push a change to one of our branches, CircleCi will check to see if all the Unit Tests provided pass.
![unit tests](https://i.imgur.com/JP6asjS.png)

### 2. Lint Testing
Lint testing is the automated checking of the source code for programmatic and stylistic errors. We need to use lint testing as when linting is implimented, it reduces bugs and impoves the overall quality of the source.

### 3. Generating Artifact
After the testing we have done, we then will store the files generated into an artifact into CricleCi with `store_artifacts`. Artifacts will ONLY be generated on the MAIN branch.

![generating artifacts](https://i.imgur.com/WBEQmsP.png)

### 4. Integration Testing
Integration testing is the phase in the software testing in which the software modules are then to be combined and then tested altogether as a gorup. Integration testing is confucted to evaluate the compliance of a system or component with specified funtional requirements.
![integration testing](https://i.imgur.com/OD4FgVx.png)

### 5. End to End testing.
Lastly, we need to implement E2E (End to End) testing. E2E testing is a technique that tests the entire software workflow from beginning to end.
![e2e testing](https://i.imgur.com/EkNH9PL.png)
![e2e artifacts](https://i.imgur.com/nTWVi8C.png)

## Multiple branches and pipeline
![git branch](https://i.imgur.com/aBXzNrJ.png)

For some reason, CircleCi won't show all the branches in the pipeline. But all branches were used in the pipeline.
![circleci pipeline](https://i.imgur.com/Ec6pR1o.png)

## Multiple Fail Scenarios
![lint testing fail](https://i.imgur.com/ptvIqSe.png)
![e2e testing fail](https://i.imgur.com/K7WvaeR.png)
![packing fail](https://i.imgur.com/G5J9ZQ9.png)
# Simple Todo App with MongoDB, Express.js and Node.js
The ToDo app uses the following technologies and javascript libraries:
* MongoDB
* Express.js
* Node.js
* express-handlebars
* method-override
* connect-flash
* express-session
* mongoose
* bcryptjs
* passport
* docker & docker-compose

## What are the features?
You can register with your email address, and you can create ToDo items. You can list ToDos, edit and delete them. 

# How to use
First install the depdencies by running the following from the root directory:

```
npm install --prefix src/
```

To run this application locally you need to have an insatnce of MongoDB running. A docker-compose file has been provided in the root director that will run an insatnce of MongoDB in docker. TO start the MongoDB from the root direction run the following command:

```
docker-compose up -d
```

Then to start the application issue the following command from the root directory:
```
npm run start --prefix src/
```

The application can then be accessed through the browser of your choise on the following:

```
localhost:5000
```

## Testing

Basic testing has been included as part of this application. This includes unit testing (Models Only), Integration Testing & E2E Testing.

### Linting:
Basic Linting is performed across the code base. To run linting, execute the following commands from the root directory:

```
npm run test-lint --prefix src/
```

### Unit Testing
Unit Tetsing is performed on the models for each object stored in MongoDB, they will vdaliate the model and ensure that required data is entered. To execute unit testing execute the following commands from the root directory:

```
npm run test-unit --prefix src/
```

### Integration Testing
Integration testing is included to ensure the applicaiton can talk to the MongoDB Backend and create a user, redirect to the correct page, login as a user and register a new task. 

Note: MongoDB needs to be running locally for testing to work (This can be done by spinning up the mongodb docker container).

To perform integration testing execute the following commands from the root directory:

```
npm run test-integration --prefix src/
```

### E2E Tests
E2E Tests are included to ensure that the website operates as it should from the users perspective. E2E Tests are executed in docker containers. To run E2E Tests execute the following commands:

```
chmod +x scripts/e2e-ci.sh
./scripts/e2e-ci.sh
```


###### This project is licensed under the MIT Open Source License
