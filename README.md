# Prisma Configuration
To configure Prisma you must have a node project created, in order to start with this configuration. This Prisma configuration is identified for a project that you want to change from an ORM Sequelize to Prisma, as well as the configuration for a new project.

For incidents in the Architecture, the prism dependencies must be installed, which would be the following command:

npm install prisma --save-dev

After installing the prisma dependencies, you have to configure and initialize the prisma

npx prisma init --datasource-provider postgres://user:password@ip:PORT/name_data_base?schema=public
 
To follow the following steps, you have to do the following commands from the root of the project to start installing and configuring it.

Steps to configure Prisma
:one: First you have to install the prisma client version

npm install @prisma/client

:two: Then you have to generate the prism schema, which is automatically created by it

npm run prisma:generate

:three: Then you have to initialize prism so that the project can be used

npx prisma init

:four: Then you have to tell it to bring all the models or schemas to the generated prisma file

npm prisma db pull -- --schema=./prisma/schema.prisma

:five: 3 scripts are configured in the package.json so that the commands can be much simpler

"prisma:sync":"npm run prisma:pull && npm run prisma:generate",
"prisma:pull":"npx prisma db pull -- --schema=./prisma/schema.prisma",
"prisma:generate": "npx prisma generate -- --schema=./prisma/schema.prisma"

Afterwards you can verify if the server has already connected to the database, and if everything seems good, the Prisma ORM is already configured correctly.
