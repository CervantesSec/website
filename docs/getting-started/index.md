# Getting started

Cervantes is an open-source, collaborative platform designed specifically for pentesters and red teams. It serves as a comprehensive management tool, streamlining the organization of projects, clients, vulnerabilities, and reports in a single, centralized location. 

By facilitating efficient data management and providing a unified workspace, Cervantes aims to significantly reduce the time and effort required in the coordination and execution of penetration testing activities.

## Installation

### With Docker <small>recommended</small> { #with-docker data-toc-label="With Docker" }

The official Docker image is a great way to get up and running in a few
minutes, as it comes with all dependencies pre-installed.

#### Requirements

- Docker
- Docker compose
- [Atlassian Jira Server](https://www.atlassian.com/es/software/jira) (Optional only if you want to use Jira Integration)

##### How to run it locally with Docker compose

* First you need to clone this repository

```sh
git clone https://github.com/CervantesSec/docker.git
```

* After that you need to start your docker containers:

```sh
docker-compose -p cervantes -f docker-compose.yml up -d
```

* After this, open your browser at http://localhost or https://localhost and you will see the Cervantes login page.

### From Source

#### Requirements

- [.NET 8](https://dotnet.microsoft.com/en-us/download/dotnet/8.0)
- [PostgreSQL](https://www.postgresql.org/)
- [Atlassian Jira Server](https://www.atlassian.com/es/software/jira) (Optional only if you want to use Jira Integration)

##### How to run it locally

To install the Cervantes application from the source code, you can follow these steps:

* **Clone the Repository**: First, you need to clone the repository from GitHub. You can do this by running the following command in your terminal:

```bash
git clone https://github.com/CervantesSec/cervantes.git
```

* **Navigate to the Project Directory**: Once the repository is cloned, navigate to the project directory:

```bash
cd Cervantes
```

* **Edit appsettings.json**: To use the application you need to edit the appsettings.json file inside the Cervantes.Web folder.

**Database Connection String**
The database connection string is used to connect your application to your database. It usually includes the server name, database name, and authentication details. Here's an example of how it might look in your `appsettings.json`:

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=myServerAddress;Database=myDataBase;Username=myUsername;Password=myPassword"
  },
}
```

Replace `myServerAddress`, `myDataBase`, `myUsername`, and `myPassword` with your actual database details.

* **Install Dependencies**: The project uses .NET 8.0, so you need to have it installed on your machine. If you don't have it, you can download it from the [official .NET website](https://dotnet.microsoft.com/en-us/download/dotnet/8.0). Once .NET is installed, you can install the project dependencies by running:

```bash
dotnet restore
```

* **Build the Project**: After the dependencies are installed, you can build the project:

```bash
dotnet build
```

* **Run the Project**: Finally, you can run the project:

```bash
dotnet run --project Cervantes.Web/Cervantes.Web.csproj
```

The application should now be running at `http://localhost:5000`.

Please note that this is a basic installation guide and the actual process might vary depending on the project's specific configuration and requirements. For example, if the project uses a database, you might need to set up the database and update the connection string in the configuration file.