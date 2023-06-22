# Step by Step guide to set up Prisma

## 1. Download prisma as dev dependency

`npm install prisma --save-dev`

## 2. Set up prisma with a database.

In our case, we are using sqlite

`npx prisma init --datasource-provider sqlite`

## 3. Add models in schema.prisma

Models in the Prisma schema have two main purposes:

1. Represent the tables in the underlying database
2. Serve as foundation for the generated Prisma Client API

## 4. Run a migration to create your database tables with Prisma Migrate

`npx prisma migrate dev --name init`

This command did two things:

1. It creates a new SQL migration file for this migration in the prisma/migrations directory.
2. It runs the SQL migration file against the database.

This command runs `prisma generate` by default

## 5. PrimsClient can be used to do operations on the database

`import { PrismaClient } from "@prisma/client";`

`const prisma = new PrismaClient();`

Use the given instance of PrismaClient to run database queries

# Other Useful prisma commands

### 1. To turn your database schema into a Prisma schema

`prisma db pull`

### 2. To create a database in accordance to your Prisma schema

`prisma db push`

### 3. To generate the Prisma Client

`prisma generate`

An instance of this client is used to do operations on database

### 4. Explore the data in Prisma Studio

`npx prisma studio`

Prisma comes with a built-in GUI to view and edit the data in your database. You can open it using the given command:
