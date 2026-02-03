Create a database migration for: `$ARGUMENTS`

1. Detect the migration framework in use:
   - Check for Prisma (`prisma/schema.prisma`), Drizzle (`drizzle.config.*`), Knex (`knexfile.*`), Sequelize (`.sequelizerc`), Alembic (`alembic.ini`), Django (`manage.py`), TypeORM (`ormconfig.*`, `data-source.*`), or raw SQL migrations
2. Look at existing migrations to understand naming conventions and patterns
3. Parse the description from $ARGUMENTS to determine the operation:
   - `add X to Y` — ALTER TABLE ADD COLUMN
   - `create X table` — CREATE TABLE
   - `remove X from Y` — ALTER TABLE DROP COLUMN
   - `rename X to Y` — ALTER TABLE RENAME
   - `add index on X` — CREATE INDEX
4. Generate the migration file:
   - Use the framework's conventions (timestamp prefix, sequential numbering, etc.)
   - Include both UP and DOWN migrations
   - Add appropriate types, constraints, and defaults
5. If using Prisma, update `schema.prisma` instead and remind to run `prisma migrate dev`
6. Show the generated migration and ask for confirmation before writing
