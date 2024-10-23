<h1 align="center">
  Medusa 2 Starter
  <br>
</h1>


This is an official Turborepo monorepo integrating a Medusa2 backend. 

## Table

- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Local Development Setup](#local-development-setup)
- [Resetting the Database](#resetting-the-database)
- [Useful Links](#useful-links)

## Prerequisites

Before you begin, ensure you have the following installed:

- ✅ Node.js 20+
- ✅ Yarn 4.5.0
- ✅ Docker and Docker Compose

## Getting Started

1. Clone this repository
2. Install dependencies:
   ```
   yarn
   ```
3. Test the setup:
   ```
   yarn build
   ```

## Local Development Setup
1. Generate `.env` files for both the Medusa backend and the Remix storefront.
   ```
   yarn run generate-env
   ```
   > This will generate the `apps/medusa/.env` and `apps/storefront/.env` files.

2. Replace the following environment variables in your `apps/medusa/.env` file:
   - `STRIPE_API_KEY` # Your Stripe secret key. Required to checkout.

3. Run the following command to initialize the Medusa database:

   ```
   yarn run medusa:init
   ```

   > This will set up the database and seed it with some initial data, including a user with the email `admin@medusa-test.com` and password `supersecret`.

4. Start the development servers:
   ```
   yarn dev
   ```

   > This will start both the Medusa backend and the Remix storefront in development mode.

5. Create a Publishable API Key for your storefront:

   - Log in to the [Medusa admin](http://localhost:9000/app/login) using the credentials `admin@medusa-test.com` / `supersecret`

   - Navigate to the [_Publishable API Keys_ settings](http://localhost:9000/app/settings/publishable-api-keys) and **copy** an exisiting API Key or create a new one with at least one Sales Channel.

## Resetting the Database
In order to reset the database, follow the steps from 3 to 7 in the Local Development Setup section.


## Useful Links

- [Medusa Documentation](https://docs.medusajs.com/)
- [Turborepo Documentation](https://turbo.build/repo/docs)
