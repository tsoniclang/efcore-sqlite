# @tsonic/efcore-sqlite

TypeScript declarations and CLR binding metadata for the EF Core SQLite provider
(`Microsoft.EntityFrameworkCore.Sqlite`) on .NET 10.

This is a generated binding package. It exposes provider APIs to TypeScript and
Tsonic while your workspace references the real NuGet assemblies.

## Install

```bash
npm install @tsonic/efcore-sqlite @tsonic/efcore @tsonic/dotnet @tsonic/core
```

## Use with Tsonic

```bash
tsonic add nuget Microsoft.EntityFrameworkCore.Sqlite <version> @tsonic/efcore-sqlite
tsonic restore
```

## Imports

Provider APIs are exported from the generated `Microsoft.EntityFrameworkCore`
namespace facade:

```ts
import { SqliteDbContextOptionsBuilderExtensions } from "@tsonic/efcore-sqlite/Microsoft.EntityFrameworkCore.js";
```

Use EF Core base types from `@tsonic/efcore`:

```ts
import { DbContextOptionsBuilder } from "@tsonic/efcore/Microsoft.EntityFrameworkCore.js";
```

## UseSqlite example

```ts
import { DbContextOptionsBuilder } from "@tsonic/efcore/Microsoft.EntityFrameworkCore.js";
import { SqliteDbContextOptionsBuilderExtensions } from "@tsonic/efcore-sqlite/Microsoft.EntityFrameworkCore.js";

const builder = new DbContextOptionsBuilder();
SqliteDbContextOptionsBuilderExtensions.UseSqlite(builder, "Data Source=app.db");
const options = builder.Options;
```

## Package shape

The package contains generated namespace facades, ESM stubs, internal
declarations, extension buckets, and `bindings.json` compiler metadata. It uses
`@tsonic/efcore`, `@tsonic/microsoft-extensions`, `@tsonic/dotnet`, and
`@tsonic/core` as peer packages for shared CLR types.

## Versioning

This repo is versioned by .NET major:

- .NET 10 → npm: `@tsonic/efcore-sqlite@10.x`

## Development

Regenerate from sibling checkouts:

```bash
npm install
./__build/scripts/generate.sh
```

The generation script requires .NET 10, `../tsbindgen`, `../dotnet`,
`../microsoft-extensions`, and `../efcore`.

## License

MIT
