# Gemini CLI Extension - Cloud SQL for SQL Server

This Gemini CLI extension provides a set of tools to interact with [Cloud SQL for SQL Server](https://cloud.google.com/sql/docs/sqlserver) instances. It allows you to manage your databases, execute queries, explore schemas, and troubleshoot issues directly from the [Gemini CLI](https://google-gemini.github.io/gemini-cli/), using natural language prompts.

## Why Use the Cloud SQL for SQL Server Extension?

* **Seamless Workflow:** As a Google-developed extension, it integrates seamlessly into the Gemini CLI environment. No need to constantly switch contexts for common database tasks.
* **Natural Language Management:** Stop wrestling with complex commands. Explore schemas and query data by describing what you want in plain English.
* **Code Generation:** Accelerate development by asking Gemini to generate data classes and other code snippets based on your table schemas.

## Prerequisites

Before you begin, ensure you have the following:

* [Gemini CLI](https://github.com/google-gemini/gemini-cli) installed.
* A Google Cloud project with the **Cloud SQL Admin API** enabled.
* IAM Permissions:
  * Cloud SQL Client (`roles/cloudsql.client`)

## Installation

To install the extension, use the command:

```bash
gemini extensions install github.com/gemini-cli-extensions/cloud-sql-sqlserver
```

## Configuration

Set the following environment variables before starting the Gemini CLI:

* `CLOUD_SQL_MSSQL_PROJECT`: The GCP project ID.
* `CLOUD_SQL_MSSQL_REGION`: The region of your Cloud SQL instance.
* `CLOUD_SQL_MSSQL_INSTANCE`: The ID of your Cloud SQL instance.
* `CLOUD_SQL_MSSQL_DATABASE`: The name of the database to connect to.
* `CLOUD_SQL_MSSQL_IP_ADDRESS`: The IP address of the Cloud SQL instance.
* `CLOUD_SQL_MSSQL_USER`: The database username.
* `CLOUD_SQL_MSSQL_PASSWORD`: The password for the database user.
* `CLOUD_SQL_MSSQL_IP_TYPE`: (Optional) The IP type i.e. “Public” or “Private” (Default: Public).

> [!NOTE]
> When using private IPs with Cloud SQL for SQL Server, you must use a Virtual Private Cloud (VPC) network.

## Usage Examples

Interact with Cloud SQL for SQL Server using natural language:

* **Explore Schemas and Data:**
  * "Show me all tables in the 'orders' database."
  * "What are the columns in the 'products' table?"
  * "How many orders were placed in the last 30 days, and what were the top 5 most purchased items?"
* **Generate Code:**
  * "Generate a Python dataclass to represent the 'customers' table."

## Supported Tools

* `list_tables`: Use this tool to list tables and descriptions.
* `execute_sql`: Use this tool to execute any SQL statement.

## Additional Extensions

Find additional extensions to support your entire software development lifecycle at [github.com/gemini-cli-extensions](https://github.com/gemini-cli-extensions).

## Troubleshooting

* "cannot execute binary file": Ensure the correct binary for your OS/Architecture has been downloaded. See [Installing the server](https://googleapis.github.io/genai-toolbox/getting-started/introduction/#installing-the-server) for more information.
