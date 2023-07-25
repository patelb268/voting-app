# Voting App with Docker - README

![image](https://github.com/patelb268/voting-app/assets/109325051/964b1e3a-fa40-4f82-b972-703c8e2c5002)


The Voting App is a sample application developed to learn Docker and showcase how different components can be containerized and orchestrated. This app allows users to vote for their favorite options, processes the votes using a .NET worker, stores the results in a PostgreSQL database, and displays the real-time results using a Node.js web application.

## Components and Technologies Used

- Web Application: Python
- In-Memory Database: Redis
- Worker: .NET
- Persistent Database: PostgreSQL
- Result Display: Node.js

## Prerequisites

Before running the Voting App, ensure you have the following installed:

- Docker: Make sure you have Docker installed on your system. You can download it from [here](https://www.docker.com/products/docker-desktop).

## Getting Started

1. Clone the repository:

       git clone <repository-url>
       cd voting-app
   
2. Build the Docker images:
   
        docker-compose build

This command will start all the containers required for the Voting App.

3. Access the application:

Web Application: Open your browser and visit http://localhost:80 to access the voting web application.
Result Display: Open your browser and visit http://localhost:3000 to see the real-time results.

## Application Architecture
The Voting App is composed of the following components:

- Web Application (Python):

    - The front-end of the application where users can vote for their favorite options.

- In-Memory Database (Redis):

    - Used to store the temporary votes before they are processed and stored in the persistent database.
  
- Worker (.NET):

    - A background worker written in .NET that processes the votes and updates the results in the PostgreSQL database.

- Persistent Database (PostgreSQL):
    - Stores the results of the votes.
    
- Result Display (Node.js):
    - Displays the real-time results of the votes using a Node.js application.

### How the App Works
- Users can access the web application (http://localhost:80) and vote for their preferred options.

- The votes are temporarily stored in the Redis in-memory database.

- The .NET worker reads the votes from Redis, processes them, and updates the results in the PostgreSQL database.

- The Node.js result display application fetches the latest vote results from the PostgreSQL database and presents them in real-time on the browser (http://localhost:3000).

### Cleaning Up
- To stop and remove the containers, network, and volumes created by the Voting App, use the following command:

```bash
docker-compose down
