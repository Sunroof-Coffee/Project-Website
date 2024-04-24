# How to Modify/Extend Software

## Making Changes

Changes can be made using a code editor, and pushed to the repository. It's suggested to use branches for feature implementation. Test thoroughly, document changes, and submit them for review and integration.

## Compiler, Languages, Build Management, Dependencies, Automated Builds

- **Compiler/Languages**: MongoDB, Express.js, React, Node.js

- **Build Management**: Frontend: Vite, Backend: Node.js

- **Dependencies**: Refer to `package.json` files in `Sunroof-Coffee`, `Sunroof-Coffee/frontend`, and `Sunroof-Coffee/backend`.

- **Automated Builds**:

  - `install-server`: `cd backend && npm install`

  - `start-server`: `cd backend && node app.js`

  - `install-frontend`: `cd frontend && npm install`

  - `build-frontend`: `cd frontend && npm run build`

  - `start-frontend`: `cd frontend && npm run dev`

## Backlog / Bug Lists

- Backlogs/Bug Lists are managed on [Jira](https://sunroof-coffee.atlassian.net/jira/software/projects/SCRUM/boards/1/backlog).

- No major issues regarding migrating to better resources or versions.

## Styling

- Use camel case for functions and variable names.

- Use kebab case for endpoints.

## Automated Testing

- Utilizes Jest and SuperTest.

- Navigate to the backend directory: `Sunroof-Coffee/backend`.

- Run the following command: `npm test`.

- Utilizes a separate test database named TestDB, which mimics the current one.

- Test file location: `Sunroof-Coffee/backend/test/menu.test.js`.

## Cloud Deployment

The three tiers of the application are hosted as follows:

- Database: MongoDB Atlas Cloud Hosting free tier (m0). The backend is connected to the database through the connection string in the environment variables.
- Backend: AWS EC2 instance. The actual backend is ran as a systemd job to allow it to accept requests even if no active terminal is open. Several scripts were written and stored in the EC2 that allow easy updating from the git repository. They are detailed in the following section.
- Frontend: AWS Amplify instance. This instance automatically rebuilds and deploys upon new commits to main. Environment variables contain the api connection string.

# How to Install

To run the site locally on your machine, you must recreate the entire tech stack. This includes the frontend, backend, and database.

## Required Software

- MongoDB, version 6.0.2 or latest
- MongoDB Compass, version 1.43.2 or latest
- Node JS, version 18.14.2 or latest
- NPM, version 9.5.0 or latest
- An IDE or text editor

## Deploying the application locally

1. Clone the provided repository at the desired location, and open the directory in your editor
2. In mongodb compass, add the 4 different data types to your local mongodb instance, and copy and paste the connection string/URI to the "MONGODB_URI" variable in the .env file in the backend directory
3. Run the following commands from the root of the repo:

- npm run install-server
- npm run install-frontend

4. Create a split terminal. Navigate the first one to the backend, and run the following command:

- npm run dev

5. Navigate the second to the frontend directory and run the following command:

- npm run dev.

6. Ensure that the port in the backend deploys onto is port 5000. If not, edit the PORT variable in backend/.env
7. Ensure the variable VITE_API_CONNECTION in frontend/.env points to port 5000.

## External Resources Used

- Square for payment handling in mobile ordering
- AWS EC2 for cloud hosting of backend
- AWS Amplify instance for serverless hosting of frontend
- MongoDB Atlas for cloud hosting of database
