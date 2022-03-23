# Api - Projeto UStart

## EF Core

Instalar a ferramenta do EF no CLI
```
dotnet tool install --global dotnet-ef
```
https://docs.microsoft.com/pt-br/ef/core/cli/dotnet

### Migrations

Antes de criar a migrations é necessário adicionar a referência do para a biblioteca do EF Design
```bash
cd Infrastructure 
dotnet add package Microsoft.EntityFrameworkCore.Design --version 5.0.2

cd API
dotnet add package Microsoft.EntityFrameworkCore.Design --version 5.0.2

dotnet clean && dotnet build
```

Como criar as migrations
```bash
cd API

#dotnet ef migrations add usuarios -c UStartContext --project ../Infrastructure/Infrastructure.csproj

#dotnet ef migrations add usuarios_nome -c UStartContext --project ../Infrastructure/Infrastructure.csproj

dotnet ef migrations add grupos_produtos -c UStartContext --project ../Infrastructure/Infrastructure.csproj

dotnet ef migrations add produtos -c UStartContext --project ../Infrastructure/Infrastructure.csproj

dotnet ef migrations add dominio-v1 -c UStartContext --project ../Infrastructure/Infrastructure.csproj
dotnet ef migrations add dominio-v2 -c UStartContext --project ../Infrastructure/Infrastructure.csproj
dotnet ef migrations add cliente_estado_id -c UStartContext --project ../Infrastructure/Infrastructure.csproj
```



https://dev.to/puritanic/how-are-you-writing-a-commit-message-1ih7#:~:text=Commit%20messages%20must%20have%20a,)%2C%20a%20colon%20and%20space.

To remember:
```
feat: a new feature for the user, not a new feature for a build script
fix: bug fix for the user, not a fix to a build scripts
refactor: refactoring production code
chore: updating gulp tasks etc.; no production code change
docs: changes to documentation
style: formatting, missing semicolons, etc.; no code change
perf: code improved in terms of processing performance
vendor: update version for dependencies, packages.
test: adding missing tests, refactoring tests; no production code change
```