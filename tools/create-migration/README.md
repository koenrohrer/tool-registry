# Create Migration

Creates database migration files following your project's migration framework and conventions. Supports Prisma, Drizzle, Knex, Sequelize, Alembic, Django, TypeORM, and raw SQL.

## Installation

Install via the [ACK extension](https://marketplace.visualstudio.com/items?itemName=koenrohrer.ack):
1. Open the ACK Marketplace panel
2. Search for "Create Migration"
3. Click Install

## Configuration

No configuration required.

## Usage

Use with: `/create-migration [description]`

Examples:
- `/create-migration add email to users`
- `/create-migration create posts table`
- `/create-migration add index on users.email`
