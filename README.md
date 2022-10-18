# Add Worker ratings

This repository contains an intentionally simplified project for you to review. It is not necessary to run the project locally, but if you choose to do it, instructions on how to accomplish this are included below.

## Brief

The context for this simulation is the following: You work at a company that powers a marketplace app for healthcare facilities to hire healthcare providers (a.k.a. workers). Your role is that of an engineering manager in the team that is in charge of the backend service responsible for worker shift management, among other things.

The engineering team is working on a new feature that will allow healthcare facilities to rate the job performed by the workers in the facility's shifts.

Your task is to review the new feature requirements, review the patch submitted by a member of your team, and provide this team member with concise feedback on any improvements that you consider for their submission. Make sure to highlight any good things in the submission, outline things you would improve or that are plain wrong, and provide an overall recommendation on how to move forward with the submission depending on what your general assessment is (e.g. approve the submission, recommend or request changes, etc.)

The requirements and specification provided to your team for delivering this feature can be found [here](./new-feature-requirements.md).

## Tips to be successful

- Your goal is to provide written feedback on a Pull Request that implements a set of changes. You will also get a chance to expand on your thoughts and discuss the submission with someone.
- Write inline comments where you deem necessary, and write a general re
- Focus your efforts on the changes in the Pull Request. Remember the project is intentionally simplified, and some aspects that would conventionally be present in a real production application are not included (e.g. authentication/authorization).
- The project already has certain design patterns in place, while they may not be ideal or follow best practices, avoid focusing on these subpar patterns for your review. Feel free to comment on them, but don't make it the focal part of your code review.
- The application uses [Prisma](https://www.prisma.io/) as an ORM layer; don't worry if you have never used Prisma before, the Prisma APIs used in this exercise are very intuitive. Most importantly, Prisma's approach to modeling the data schema should be easy to follow, you can check the project's [data schema here](./prisma/schema.prisma).

## Helpful links

- As mentioned above, make sure you take a look to [the data schema](./prisma/schema.prisma) so you have this reference handy.
- The application exposes a REST API, which is defined in an Open API (formerly known as Swagger) schema, also [included in the project](./src/rest/v1/openapi.yml).
- The [Swagger Editor](https://editor.swagger.io/) is a great resource for exploring the Open API schema, copy and paste it the contents of the Open API schema in the editor to easily navigate it.

## Local Setup

Pre-requisites:

- Node.js version 16+ (https://nodejs.org/en/download/)
- Docker (https://docs.docker.com/get-docker/)
- docker-compose (https://docs.docker.com/compose/install/)

Clone the repository, `cd` into it, then run:

```sh
> $ npm i
```

The repository comes with a docker-compose.yml file to easily run PostgreSQL, to spin this up:

```sh
> $ docker-compose up -d
```

You should be able to connect to Postgres using any client at localhost:5432 (the default Postgres port). The credentials can be found in the `docker-compose.yml` file and in the `.env.sample` file. Make a copy of `.env.sample` and name it `.env`:

```sh
> $ cp .env.sample .env
```

Apply DB migrations with:

```sh
> $ npx prisma migrate dev
```

And finally, run the server with:

```sh
> $ npm start
```
