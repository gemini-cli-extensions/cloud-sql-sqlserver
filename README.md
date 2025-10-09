# Gemini CLI Extension - Cloud SQL for SQL Server

> [!NOTE]
> This extension is currently in beta (pre-v1.0), and may see breaking changes until the first stable release (v1.0).

This Gemini CLI extension provides a set of tools to interact with [Cloud SQL for SQL Server](https://cloud.google.com/sql/docs/sqlserver) instances. It allows you to manage your databases, execute queries, explore schemas, and troubleshoot issues directly from the [Gemini CLI](https://google-gemini.github.io/gemini-cli/), using natural language prompts.

Learn more about [Gemini CLI Extensions](https://github.com/google-gemini/gemini-cli/blob/main/docs/extensions/index.md).

## Why Use the Cloud SQL for SQL Server Extension?

* **Seamless Workflow:** As a Google-developed extension, it integrates seamlessly into the Gemini CLI environment. No need to constantly switch contexts for common database tasks.
* **Natural Language Management:** Stop wrestling with complex commands. Explore schemas and query data by describing what you want in plain English.
* **Code Generation:** Accelerate development by asking Gemini to generate data classes and other code snippets based on your table schemas.

## Prerequisites

Before you begin, ensure you have the following:

* [Gemini CLI](https://github.com/google-gemini/gemini-cli) installed with version **+v0.6.0**.
* A Google Cloud project with the **Cloud SQL Admin API** enabled.
* IAM Permissions:
  * Cloud SQL Client (`roles/cloudsql.client`)
  * Cloud SQL Viewer (`roles/cloudsql.viewer`)
  * Cloud SQL Admin (`roles/cloudsql.admin`)

## Getting Started

### Installation

To install the extension, use the following command before starting the Gemini CLI:

```bash
gemini extensions install https://github.com/gemini-cli-extensions/cloud-sql-sqlserver
```

### Configuration

Set the following environment variables before starting the Gemini CLI.
This configuration is not required if utilizing the [Admin toolset](#supported-tools).

* `CLOUD_SQL_MSSQL_PROJECT`: The GCP project ID.
* `CLOUD_SQL_MSSQL_REGION`: The region of your Cloud SQL instance.
* `CLOUD_SQL_MSSQL_INSTANCE`: The ID of your Cloud SQL instance.
* `CLOUD_SQL_MSSQL_DATABASE`: The name of the database to connect to.
* `CLOUD_SQL_MSSQL_IP_ADDRESS`: The IP address of the Cloud SQL instance.
* `CLOUD_SQL_MSSQL_USER`: The database username.
* `CLOUD_SQL_MSSQL_PASSWORD`: The password for the database user.
* `CLOUD_SQL_MSSQL_IP_TYPE`: (Optional) The IP type i.e. “Public” or “Private” (Default: Public).

Ensure [Application Default Credentials](https://cloud.google.com/docs/authentication/gcloud) are available in your environment.

> [!NOTE]
> If your Cloud SQL for SQL Server instance uses private IPs, you must run Gemini CLI in the same Virtual Private Cloud (VPC) network.

### Start Gemini CLI

To start the Gemini CLI, use the following command:

```bash
gemini
```

> [!WARNING]
> **Changing Instance & Database Connections**
> Currently, the database connection must be configured before starting the Gemini CLI and can not be changed during a session.
> To save and resume conversation history use command: `/chat save <tag>` and `/chat resume <tag>`.

### Start Gemini CLI

To start the Gemini CLI, use the following command:

```bash
gemini
```

> [!WARNING]
> **Changing Instance & Database Connections**
> Currently, the database connection must be configured before starting the Gemini CLI and can not be changed during a session.
> To save and resume conversation history use command: `/chat save <tag>` and `/chat resume <tag>`.

### Start Gemini CLI

To start the Gemini CLI, use the following command:

```bash
gemini
```

> [!WARNING]
> **Changing Instance & Database Connections**
> Currently, the database connection must be configured before starting the Gemini CLI and can not be changed during a session.
> To save and resume conversation history use command: `/chat save <tag>` and `/chat resume <tag>`.

### Start Gemini CLI

To start the Gemini CLI, use the following command:

```bash
gemini
```

> [!WARNING]
> **Changing Instance & Database Connections**
> Currently, the database connection must be configured before starting the Gemini CLI and can not be changed during a session.
> To save and resume conversation history use command: `/chat save <tag>` and `/chat resume <tag>`.

## Usage Examples

Interact with Cloud SQL for SQL Server using natural language:

* **Provision Infrastructure:**
   * "Create a new Cloud SQL for SQL Server instance named 'e-commerce-prod' in the 'my-gcp-project' project."
   * "Create a new user named 'analyst' with read access to all tables."
* **Explore Schemas and Data:**
  * "Show me all tables in the 'orders' database."
  * "What are the columns in the 'products' table?"
  * "How many orders were placed in the last 30 days, and what were the top 5 most purchased items?"
* **Generate Code:**
  * "Generate a Python dataclass to represent the 'customers' table."

## Supported Tools

*   **Admin:**
   	* `create_instance`: Use this tool to create an SQL Server instance.
   	* `create_user`: Use this tool to create SQL Server-BUILT-IN or IAM-based users.
   	* `get_instance`: Use this tool to get details about an SQL Server instance.
   	* `get_user`: Use this tool to get details about a user.
   	* `list_instances`: Use this tool to list instances in a given project and location.
   	* `list_users`: Use this tool to list users in a given project and location.
    * `wait_for_operation`: Use this tool to poll the operations API until the operation is done.

*   **Data:**
    * `list_tables`: Use this tool to list tables and descriptions.
    * `execute_sql`: Use this tool to execute any SQL statement.

## Additional Extensions

Find additional extensions to support your entire software development lifecycle at [github.com/gemini-cli-extensions](https://github.com/gemini-cli-extensions), including:
* [Generic SQL Server extension](https://github.com/gemini-cli-extensions/sql-server)
* [Cloud SQL for SQL Server Observability extension](https://github.com/gemini-cli-extensions/cloud-sql-sqlserver-observability)
* and more!

## Troubleshooting

* "✖ Error during discovery for server: MCP error -32000: Connection closed": The database connection has not been established. Ensure your configuration is set via environment variables.
* "✖ MCP ERROR: Error: spawn /Users/<USER>/.gemini/extensions/cloud-sql-sqlserver/toolbox ENOENT": The Toolbox binary did not download correctly. Ensure you are using Gemini CLI v0.6.0+.
* "cannot execute binary file": The Toolbox binary did not download correctly. Ensure the correct binary for your OS/Architecture has been downloaded. See [Installing the server](https://googleapis.github.io/genai-toolbox/getting-started/introduction/#installing-the-server) for more information.
