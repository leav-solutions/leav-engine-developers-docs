# Core

{% hint style="info" %}
Configuration folder: `apps/core/config`
{% endhint %}

_All mandatory settings have no default value and must be provided._

### Server

| Environment variable         | Description                            |      Default value     | Mandatory |
| ---------------------------- | -------------------------------------- | :--------------------: | :-------: |
| SERVER\_HOST                 | Server host                            |        localhost       |           |
| SERVER\_PORT                 | Server port                            |          4001          |           |
| SERVER\_PUBLIC\_URL          | Public URL                             |  http://localhost:4001 |           |
| SERVER\_WS\_URL              | Websocket URL                          |   ws://localhost:4001  |           |
| API\_ENDPOINT                | GraphQL API endpoint                   |         graphql        |           |
| SERVER\_ALLOW\_INTROSPECTION | Allow GraphQL introspection queries    |          true          |           |
| SERVER\_UPLOAD\_LIMIT        | Upload limit                           |          100mb         |           |
| SERVER\_SUPPORT\_EMAIL       | Email shown in "contact support" links |                        |     \*    |
| SERVER\_ADMIN\_LOGIN         | Admin default login                    |                        |     \*    |
| SERVER\_ADMIN\_PASSWORD      | Admin default password                 |                        |     \*    |
| SERVER\_ADMIN\_EMAIL         | Admin default email                    |                        |     \*    |
| SERVER\_SYSTEM\_USER\_EMAIL  | System user default email              | system@leav-engine.com |           |

### ArangoDB

| Environment variable | Description                                   | Default value | Mandatory |
| -------------------- | --------------------------------------------- | :-----------: | :-------: |
| ARANGO\_URL          | ArangoDB URL, including username and password |               |     \*    |
| DB\_NAME             | Database name                                 |               |     \*    |

### Cache

| Environment variable   | Description                               | Default value | Mandatory |
| ---------------------- | ----------------------------------------- | :-----------: | :-------: |
| DISK\_CACHE\_DIRECTORY | Directory where disk cache will be stored |     /cache    |           |

### Elastic Search

| Environment variable | Description        |       Default value       | Mandatory |
| -------------------- | ------------------ | :-----------------------: | :-------: |
| ELASTICSEARCH\_URL   | Elastic Search URL | http://elasticsearch:9200 |           |

### Authentication

| Environment variable   | Description                                    | Default value | Mandatory |
| ---------------------- | ---------------------------------------------- | :-----------: | :-------: |
| AUTH\_KEY              | Key used to generate authentication token      |               |     \*    |
| TOKEN\_TTL             | Authentication token Time To Live              |       7d      |           |
| AUTH\_COOKIE\_SAMESITE | `samesite` settings for authentication cookies |      lax      |           |
| AUTH\_COOKIE\_SECURE   | `secure` flag for authentication cookies       |     false     |           |
| AUTH\_RESET\_PWD\_TTL  | "Reset password" time to live                  |      20m      |           |

### Sending emails

| Environment variable | Description                              | Default value | Mandatory |
| -------------------- | ---------------------------------------- | :-----------: | :-------: |
| MAILER\_HOST         | Host of server for sending emails        |   localhost   |           |
| MAILER\_PORT         | Port of server for sending emails        |      587      |           |
| MAILER\_SECURE       | Use secure connection for sending emails |     false     |           |
| MAILER\_AUTH\_USER   | Emails server username                   |               |     \*    |
| MAILER\_AUTH\_PWD    | Emails server password                   |               |     \*    |

### Languages

| Environment variable | Description         | Default value | Mandatory |
| -------------------- | ------------------- | :-----------: | :-------: |
| LANG\_AVAILABLE      | Available languages | \['fr', 'en'] |           |
| LANG\_DEFAULT        | Default language    |       fr      |           |

### Logs

| Environment variable | Description                                                                  | Default value |             Mandatory             |
| -------------------- | ---------------------------------------------------------------------------- | :-----------: | :-------------------------------: |
| LOG\_LEVEL           | Log level ([more info](https://github.com/winstonjs/winston#logging-levels)) |      info     |                                   |
| LOG\_TRANSPORT       | Log transport (Comma separated list of transport, including : console, file) |  console,file |                                   |
| LOG\_FILE            | Log destination file                                                         |               | \* (if transport includes "file") |

### RabbitMQ

| Environment variable | Description                                                                                           | Default value | Mandatory |
| -------------------- | ----------------------------------------------------------------------------------------------------- | :-----------: | :-------: |
| AMQP\_HOST           | Host of RabbitMQ server                                                                               |               |     \*    |
| AMQP\_USERNAME       | Username of RabbitMQ server                                                                           |               |     \*    |
| AMQP\_PWD            | Password of RabbitMQ server                                                                           |               |     \*    |
| AMQP\_PORT           | Port of RabbitMQ server                                                                               |      5672     |           |
| AMQP\_EXCHANGE       | Exchange name where RabbitMQ messages are sent                                                        |   leav\_core  |           |
| AMQP\_TYPE           | Type of exchange for messages routing ([more info](https://www.rabbitmq.com/publishers.html#routing)) |     direct    |           |
| AMQP\_PREFETCH       | Number of messages fetched simultaneously                                                             |       5       |           |

### Redis

| Environment variable | Description                     | Default value | Mandatory |
| -------------------- | ------------------------------- | :-----------: | :-------: |
| REDIS\_HOST          | Host of Redis server            |       \*      |           |
| REDIS\_PORT          | Port of Redis server            |       \*      |           |
| REDIS\_DATABASE      | Database number on Redis server |       0       |           |

### Files manager

| Environment variable         | Description                                                                     |       Default value      | Mandatory |
| ---------------------------- | ------------------------------------------------------------------------------- | :----------------------: | :-------: |
| FM\_EVENTS\_QUEUE            | Queue for files events                                                          |       files\_events      |           |
| FM\_PREVIEW\_REQUEST\_QUEUE  | Queue for preview requests messages                                             |  files\_preview\_request |           |
| FM\_PREVIEW\_RESPONSE\_QUEUE | Queue for preview response messages                                             | files\_preview\_response |           |
| FM\_USER\_ID                 | ID of user used for all files related actions (eg. create records, update, ...) |      2 (system user)     |           |
| FM\_USER\_GROUPS\_IDS        | ID of group for user used for all files related actions                         |  1 (files admins group)  |           |
| FILES\_ROOT\_PATHS           | Files root path by root key (eg. files1:/files,files2:/other\_files\_folder     |       files1:/files      |           |
| FILES\_ORIGINALS\_PREFIX     | Public path prefix for original files URL                                       |         originals        |           |

### Tasks manager

| Environment variable | Description                                        |       Default value      | Mandatory |
| -------------------- | -------------------------------------------------- | :----------------------: | :-------: |
| TM\_NB\_WORKERS      | Number of simultaneous workers                     | Number of CPUs available |           |
| TM\_ORDERS\_QUEUE    | Queue for tasks orders (eg. creation, cancel, ...) |       tasks\_orders      |           |

### Debug more

| Environment variable | Description       | Default value | Mandatory |
| -------------------- | ----------------- | :-----------: | :-------: |
| DEBUG                | Enable debug mode |     false     |           |

### Export

| Environment variable | Description                             | Default value | Mandatory |
| -------------------- | --------------------------------------- | :-----------: | :-------: |
| EXPORT\_DIR          | Directory where export files are stored |    /exports   |           |

### Import

| Environment variable | Description                                                                                                                                                                                      | Default value | Mandatory |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :-----------: | :-------: |
| IMPORT\_DIR          | Directory where import files are stored                                                                                                                                                          |    /imports   |           |
| IMPORT\_SIZE\_LIMIT  | Limit size (in megabytes) where the JSON file syntax is checked. This process requires a lot of memory. Setting this limit too high may make the whole process to crash if we reach memory limit |       10      |           |
| IMPORT\_GROUP\_DATA  | Number of elements processed simultaneously, to limit load on database server                                                                                                                    |       50      |           |

### Previews

| Environment variable | Description                                                         | Default value | Mandatory |
| -------------------- | ------------------------------------------------------------------- | :-----------: | :-------: |
| PREVIEWS\_DIRECTORY  | Directory where previews generated by previews generator are stored |    /results   |           |

### Applications

| Environment variable | Description                                                | Default value | Mandatory |
| -------------------- | ---------------------------------------------------------- | :-----------: | :-------: |
| APPLICATIONS\_FOLDER | Directory where applications instances (builds) are stored |  applications |           |

### DB Profiling

| Environment variable | Description                                                                                                                                       | Default value | Mandatory |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | :-----------: | :-------: |
| DB\_PROFILER\_ENABLE | Enable database profiling. This will add a "dbProfiler" section in all API calls. **Do not use in production** as it slows down every calls to DB |               |           |

__
