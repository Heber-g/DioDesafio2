# Megaman Bosses API

## Descrição
Esta API foi desenvolvida em .NET Core 3.1 para listar os bosses da franquia Megaman. O objetivo é fornecer um backend que retorna informações sobre os bosses no formato JSON.

## Formato de Resposta
A API retorna dados no seguinte formato:

```json
{
  "Id": 1,
  "Code": "DLN/DRN-003",
  "Name": "Cutman",
  "HP": 150,
  "Picture": "https://vignette.wikia.nocookie.net/megaman/images/2/22/Cutman.png"
}
```

## Tecnologias Utilizadas
- [.NET Core 3.1](https://dotnet.microsoft.com/en-us/download/dotnet/3.1)
- [Entity Framework Core 3.1.8](https://learn.microsoft.com/en-us/ef/core/)
- [SQL Server](https://www.microsoft.com/pt-br/sql-server)
- [Newtonsoft.Json 12.0.2](https://www.newtonsoft.com/json)

## Estrutura do Projeto
A estrutura do projeto segue o seguinte formato:

```
.vs
.vscode
bin
Controllers
Database
middlewares
Models
obj
Properties
Services
appsettings.Development.json
appsettings.json
global.json
MegamanApi.csproj
MegamanApi.sln
Program.cs
Startup.cs
```

## Pré-requisitos
Antes de executar a aplicação, certifique-se de ter instalado:
- [.NET Core SDK 3.1](https://dotnet.microsoft.com/en-us/download/dotnet/3.1)
- [SQL Server](https://www.microsoft.com/pt-br/sql-server) ou outro banco compatível com o Entity Framework
- [Git](https://git-scm.com/downloads)

## Como Executar o Projeto
1. Clone este repositório:
   ```sh
   git clone https://github.com/seu-repositorio.git
   ```
2. Navegue até o diretório do projeto:
   ```sh
   cd nome-do-projeto
   ```
3. Restaure as dependências:
   ```sh
   dotnet restore
   ```
4. Configure a conexão com o banco de dados no arquivo `appsettings.json`.
5. Aplique as migrações do banco de dados:
   ```sh
   dotnet ef database update
   ```
6. Execute a aplicação:
   ```sh
   dotnet run
   ```

## Endpoints
### Listar todos os bosses
```http
GET /api/bosses
```
**Resposta:**
```json
[
  {
    "Id": 1,
    "Code": "DLN/DRN-003",
    "Name": "Cutman",
    "HP": 150,
    "Picture": "https://vignette.wikia.nocookie.net/megaman/images/2/22/Cutman.png"
  },
  ...
]
```

### Buscar um boss por ID
```http
GET /api/bosses/{id}
```
**Resposta:**
```json
{
  "Id": 1,
  "Code": "DLN/DRN-003",
  "Name": "Cutman",
  "HP": 150,
  "Picture": "https://vignette.wikia.nocookie.net/megaman/images/2/22/Cutman.png"
}
```

### Criar um novo boss
```http
POST /api/bosses
```
**Corpo da Requisição:**
```json
{
  "Code": "DLN/DRN-004",
  "Name": "Gutsman",
  "HP": 200,
  "Picture": "https://vignette.wikia.nocookie.net/megaman/images/4/44/Gutsman.png"
}
```
**Resposta:**
```json
{
  "Id": 2,
  "Code": "DLN/DRN-004",
  "Name": "Gutsman",
  "HP": 200,
  "Picture": "https://vignette.wikia.nocookie.net/megaman/images/4/44/Gutsman.png"
}
```

## Testes
Para executar os testes unitários do projeto:
```sh
 dotnet test
```

## Contribuição
Contribuições são bem-vindas! Siga os seguintes passos:
1. Faça um fork do repositório
2. Crie uma nova branch (`git checkout -b feature/nova-feature`)
3. Commit suas alterações (`git commit -m 'Adicionando nova feature'`)
4. Envie para o repositório remoto (`git push origin feature/nova-feature`)
5. Abra um Pull Request

## Licença
Este projeto é licenciado sob a MIT License. Para mais detalhes, consulte o arquivo LICENSE.

