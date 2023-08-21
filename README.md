# API with PRISMA

A backend API as first steps with Prisma ORM

## How To Use
### Preconditions
- Install Postgres & PgAdmin 4 and configure them first.
- Create a `.env` file in root project.
- In `.env` file, create and set the env variable: `DATABASE_URL` according to the following syntaxis:
  `"postgresql://USER:PASSWORD@HOST:PORT/DATABASE?schema=SCHEMA"`

## PrismaORM Settings
- Check or create the directory prisma/schema.prisma for modifications.
- Install VSCode extension for prisma and configure format for directory .vscode/settings.json
- Run the command `npx prisma migrate dev`
- Then, run the command `npx prisma studio` once the above is finished (Use Google Chrome to run this command).
- Check through PgAdmin 4 there is a database with the url given in `.env` file and go to Databases -> DATABASE (name given in url) -> Schemas -> public -> tables and User DB should appear.
- Run the command `npx prisma migrate reset`, this is useful to reset the DB.

### Run the Project
- Install dependencies: `npm i` or `npm install`
- Run the Project: `npm run dev`
- Terminal should show that `Server is running on port [PORT_NUMBER]` (Port is 8000 in this case).

### Testing
- The server URL is `http://localhost:[PORT_NUMBER]`
- Check that the server uses the url parameter: `http://localhost:[PORT_NUMBER]/api/healthcheck`
- In REST API client should show through get request: `"Server is running - Status OK"`
- For User Entity is using url param: `/api/users` and the following params and http requests for CRUD:
  | Route | HTTP Verb | Description | Request Body |
  | --- | --- | --- | --- |
  | / | POST | Creates a new user | User data |
  | /:id | PUT | Updates an existing user | User data and ID parameter |
  | / | GET | Retrieves all users | N/A |
  | /:id | GET | Retrieves a single user by ID | ID parameter |
  | /:id | DELETE | Deletes a user by ID | ID parameter |