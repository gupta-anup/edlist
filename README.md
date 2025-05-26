# Project Management Dashboard

## Technology Stack

- **Frontend**: Next.js, Tailwind CSS, Redux Toolkit, Redux Toolkit Query, Material UI Data Grid
- **Backend**: Node.js with Express, Prisma (PostgreSQL ORM)
- **Database**: PostgreSQL, managed with PgAdmin
- **Cloud**: AWS EC2, AWS RDS, AWS API Gateway, AWS Amplify, AWS S3, AWS Lambda, AWS Cognito

## Getting Started

### Prerequisites

Ensure you have these tools installed:

- Git
- Node.js
- npm (Node Package Manager)
- PostgreSQL ([download](https://www.postgresql.org/download/))
- PgAdmin ([download](https://www.pgadmin.org/download/))

### Installation Steps

1. Clone the repository:
   `git clone [git url]`
   `cd project-management`

2. Install dependencies in both client and server:
   `cd client`
   `npm i`
   `cd ..`
   `cd server`
   `npm i`

3. Configure environment variables:

   `.env` for server settings (PORT, DATABASE_URL)
   `.env.local` for client settings (NEXT_PUBLIC_API_BASE_URL, NEXT_PUBLIC_COGNITO_USER_POOL_ID, NEXT_PUBLIC_COGNITO_USER_POOL_CLIENT_ID)

4. Set up the database:
   `npx prisma generate`
   `npx prisma migrate dev --name init`
   `npm run seed`

5. Run the project
   `npm run dev`

## Additional Resources

### Diagrams and Models

- [Data model diagram](https://lucid.app/lucidchart/b4a745a0-cc5e-4d64-81c0-a7123d7c3b5f/edit?invitationId=inv_7c25661a-a232-4b65-87c4-9b4566bbfff1)
- [AWS architecture diagram](https://lucid.app/lucidchart/57a7caa2-29e1-42cd-b8b2-bad522632100/edit?invitationId=inv_95a01d84-1b41-484c-a9b7-215002914cea)
- [AWS Cognito flow diagram](https://lucid.app/lucidchart/61796402-915e-4c6a-8701-733a1a4134ee/edit?viewport_loc=387%2C1187%2C1867%2C900%2C0_0&invitationId=inv_360f93a8-5e88-4f74-bc70-0c5dc3fbca06)

### Database Management Commands

- Command for resetting ID in database:
  ```sql
  SELECT setval(pg_get_serial_sequence('"[DATA_MODEL_NAME_HERE]"', 'id'), coalesce(max(id)+1, 1), false) FROM "[DATA_MODEL_NAME_HERE]";
  ```
