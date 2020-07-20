# Migration `20200225132359-example`

This migration has been generated by Errorname at 2/25/2020, 1:23:59 PM.
You can check out the [state of the schema](./schema.prisma) after the migration.

## Database Steps

```sql
CREATE TABLE "quaint"."User" (
    "email" TEXT NOT NULL DEFAULT '' ,
    "id" INTEGER NOT NULL  PRIMARY KEY AUTOINCREMENT,
    "name" TEXT   
) 

CREATE UNIQUE INDEX "quaint"."User.email" ON "User"("email")
```

## Changes

```diff
diff --git schema.prisma schema.prisma
migration ..20200225132359-example
--- datamodel.dml
+++ datamodel.dml
@@ -1,0 +1,17 @@
+// This is your Prisma schema file,
+// learn more about it in the docs: https://pris.ly/d/prisma-schema
+
+datasource db {
+  provider = "sqlite"
+  url      = env("DATABASE_URL")
+}
+
+generator client {
+  provider = "prisma-client-js"
+}
+
+model User {
+  id    Int     @id @default(autoincrement())
+  email String  @unique
+  name  String?
+}
```

