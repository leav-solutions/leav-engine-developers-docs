# Configuration

Each service has its own JavaScript configuration files.

Default configuration can be overridden in 2 ways:

* Providing a `local.js` file in service config folder.\
  Settings specified in this file will override default ones (more info [here](https://github.com/leav-solutions/leav-engine/tree/master/libs/config-manager)).
* Setting environment variables at runtime

### Core

Configuration folder: `apps/core/config`

#### Available settings

_All mandatory settings have no default value and must be provided._

| Environment variable         | Description                                                                                                                                                                                      |           Default value           | Mandatory |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :-------------------------------: | :-------: |
|                              |                                                                                                                                                                                                  |                                   |           |
| **Core server**              |                                                                                                                                                                                                  |                                   |           |
| SERVER\_HOST                 | Server host                                                                                                                                                                                      |             localhost             |           |
| SERVER\_PORT                 | Server port                                                                                                                                                                                      |                4001               |           |
| SERVER\_PUBLIC\_URL          | Public URL                                                                                                                                                                                       |       http://localhost:4001       |           |
| SERVER\_WS\_URL              | Websocket URL                                                                                                                                                                                    |       http://localhost:4001       |           |
| API\_ENDPOINT                | GraphlQL API endpoint                                                                                                                                                                            |              graphql              |           |
| SERVER\_ALLOW\_INTROSPECTION | Allow GraphQL introspection queries                                                                                                                                                              |                true               |           |
| SERVER\_UPLOAD\_LIMIT        | Upload limit                                                                                                                                                                                     |               100mb               |           |
| SERVER\_SUPPORT\_EMAIL       | Email shown in "contact support" links                                                                                                                                                           |                 \*                |           |
| SERVER\_ADMIN\_LOGIN         | Admin default login                                                                                                                                                                              |                 \*                |           |
| SERVER\_ADMIN\_PASSWORD      | Admin default password                                                                                                                                                                           |                 \*                |           |
| SERVER\_ADMIN\_EMAIL         | Admin default email                                                                                                                                                                              |                 \*                |           |
| SERVER\_SYSTEM\_USER\_EMAIL  | System user default email                                                                                                                                                                        |       system@leav-engine.com      |           |
|                              |                                                                                                                                                                                                  |                                   |           |
| **ArangoDB**                 |                                                                                                                                                                                                  |                                   |           |
| ARANGO\_URL                  | ArangoDB URL, including username and password                                                                                                                                                    |                 \*                |           |
| DB\_NAME                     | Database name                                                                                                                                                                                    |                 \*                |           |
|                              |                                                                                                                                                                                                  |                                   |           |
| **Cache**                    |                                                                                                                                                                                                  |                                   |           |
| DISK\_CACHE\_DIRECTORY       | Directory where disk cache will be stored                                                                                                                                                        |               /cache              |           |
|                              |                                                                                                                                                                                                  |                                   |           |
| **Elastic Search**           |                                                                                                                                                                                                  |                                   |           |
| ELASTICSEARCH\_URL           | Elastic Search URL                                                                                                                                                                               |     http://elasticsearch:9200     |           |
|                              |                                                                                                                                                                                                  |                                   |           |
| **Authentication**           |                                                                                                                                                                                                  |                                   |           |
| AUTH\_KEY                    | Key used to generate authentication token                                                                                                                                                        |                 \*                |           |
| TOKEN\_TTL                   | Authentication token Time To Live                                                                                                                                                                |                 7d                |           |
| AUTH\_COOKIE\_SAMESITE       | `samesite` settings for authentication cookies                                                                                                                                                   |                lax                |           |
| AUTH\_COOKIE\_SECURE         | `secure` flag for authentication cookies                                                                                                                                                         |               false               |           |
| AUTH\_RESET\_PWD\_TTL        | "Reset password" time to live                                                                                                                                                                    |                20m                |           |
|                              |                                                                                                                                                                                                  |                                   |           |
| **Sending emails**           |                                                                                                                                                                                                  |                                   |           |
| MAILER\_HOST                 | Host of server for sending emails                                                                                                                                                                |             localhost             |           |
| MAILER\_PORT                 | Port of server for sending emails                                                                                                                                                                |                587                |           |
| MAILER\_SECURE               | Use secure connection for sending emails                                                                                                                                                         |               false               |           |
| MAILER\_AUTH\_USER           | Emails server username                                                                                                                                                                           |                 \*                |           |
| MAILER\_AUTH\_PWD            | Emails server password                                                                                                                                                                           |                 \*                |           |
|                              |                                                                                                                                                                                                  |                                   |           |
| **Languages**                |                                                                                                                                                                                                  |                                   |           |
| LANG\_AVAILABLE              | Available languages                                                                                                                                                                              |           \['fr', 'en']           |           |
| LANG\_DEFAULT                | Default language                                                                                                                                                                                 |                 fr                |           |
|                              |                                                                                                                                                                                                  |                                   |           |
| **Logs**                     |                                                                                                                                                                                                  |                                   |           |
| LOG\_LEVEL                   | Log level ([more info](https://github.com/winstonjs/winston#logging-levels))                                                                                                                     |                info               |           |
| LOG\_TRANSPORT               | Log transport (Comma separated list of transport, including : console, file)                                                                                                                     |            console,file           |           |
| LOG\_FILE                    | Log destination file                                                                                                                                                                             | \* (if transport includes "file") |           |
|                              |                                                                                                                                                                                                  |                                   |           |
| **RabbitMQ**                 |                                                                                                                                                                                                  |                                   |           |
| AMQP\_HOST                   | Host of RabbitMQ server                                                                                                                                                                          |                 \*                |           |
| AMQP\_USERNAME               | Username of RabbitMQ server                                                                                                                                                                      |                 \*                |           |
| AMQP\_PWD                    | Password of RabbitMQ server                                                                                                                                                                      |                 \*                |           |
| AMQP\_PORT                   | Port of RabbitMQ server                                                                                                                                                                          |                5672               |           |
| AMQP\_EXCHANGE               | Exchange name where RabbitMQ messages are sent                                                                                                                                                   |             leav\_core            |           |
| AMQP\_TYPE                   | Type of exchange for messages routin ([more info](https://www.rabbitmq.com/publishers.html#routing))                                                                                             |               direct              |           |
| AMQP\_PREFETCH               | Number of messages fetched simultaneously                                                                                                                                                        |                 5                 |           |
|                              |                                                                                                                                                                                                  |                                   |           |
| **Redis**                    |                                                                                                                                                                                                  |                                   |           |
| REDIS\_HOST                  | Host of Redis server                                                                                                                                                                             |                 \*                |           |
| REDIS\_PORT                  | Port of Redis server                                                                                                                                                                             |                 \*                |           |
| REDIS\_DATABASE              | Database number on Redis server                                                                                                                                                                  |                 0                 |           |
|                              |                                                                                                                                                                                                  |                                   |           |
| **Files manager**            |                                                                                                                                                                                                  |                                   |           |
| FM\_EVENTS\_QUEUE            | Queue for files events                                                                                                                                                                           |           files\_events           |           |
| FM\_PREVIEW\_REQUEST\_QUEUE  | Queue for preview requests messages                                                                                                                                                              |      files\_preview\_request      |           |
| FM\_PREVIEW\_RESPONSE\_QUEUE | Queue for preview response messages                                                                                                                                                              |      files\_preview\_response     |           |
| FM\_USER\_ID                 | ID of user used for all files related actions (eg. create records, update, ...)                                                                                                                  |          2 (system user)          |           |
| FM\_USER\_GROUPS\_IDS        | ID of group for user used for all files related actions                                                                                                                                          |       1 (files admins group)      |           |
| FILES\_ROOT\_PATHS           | Files root path by root key (eg. files1:/files,files2:/other\_files\_folder                                                                                                                      |           files1:/files           |           |
| FILES\_ORIGINALS\_PREFIX     | Public path prefix for original files URL                                                                                                                                                        |             originals             |           |
|                              |                                                                                                                                                                                                  |                                   |           |
| **Tasks manager**            |                                                                                                                                                                                                  |                                   |           |
| TM\_NB\_WORKERS              | Number of simultaneous workers                                                                                                                                                                   |      Number of CPUs available     |           |
| TM\_ORDERS\_QUEUE            | Queue for tasks orders (eg. creation, cancel, ...)                                                                                                                                               |           tasks\_orders           |           |
|                              |                                                                                                                                                                                                  |                                   |           |
| **Debug more**               |                                                                                                                                                                                                  |                                   |           |
| DEBUG                        | Enable debug mode                                                                                                                                                                                |               false               |           |
|                              |                                                                                                                                                                                                  |                                   |           |
| **Export**                   |                                                                                                                                                                                                  |                                   |           |
| EXPORT\_DIR                  | Directory where export files are stored                                                                                                                                                          |              /exports             |           |
|                              |                                                                                                                                                                                                  |                                   |           |
| **Import**                   |                                                                                                                                                                                                  |                                   |           |
| IMPORT\_DIR                  | Directory where import files are stored                                                                                                                                                          |              /imports             |           |
| IMPORT\_SIZE\_LIMIT          | Limit size (in megabytes) where the JSON file syntax is checked. This process requires a lot of memory. Setting this limit too high may make the whole process to crash if we reach memory limit |                 10                |           |
| IMPORT\_GROUP\_DATA          | Number of elements processed simultaneously, to limit load on database server                                                                                                                    |                 50                |           |
|                              |                                                                                                                                                                                                  |                                   |           |
| **Previews**                 |                                                                                                                                                                                                  |                                   |           |
| PREVIEWS\_DIRECTORY          | Directory where previews generated by previews generator are stored                                                                                                                              |              /results             |           |
|                              |                                                                                                                                                                                                  |                                   |           |
| **Applications**             |                                                                                                                                                                                                  |                                   |           |
| APPLICATIONS\_FOLDER         | Directory where applications instances (builds) are stored                                                                                                                                       |            applications           |           |
|                              |                                                                                                                                                                                                  |                                   |           |
| **DB Profiling**             |                                                                                                                                                                                                  |                                   |           |
| DB\_PROFILER\_ENABLE         | Enable database profiling. This will add a "dbProfiler" section in all API calls. Do not use in production as it slows down every calls to DB                                                    |                                   |           |

### Automate Scan

Configuration folder: `apps/automate-scan/config`

#### Available settings

_All mandatory settings have no default value and must be provided._

| Environment variable      | Description                                                                                                                                                                                          |     Default value    | Mandatory |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------: | :-------: |
|                           |                                                                                                                                                                                                      |                      |           |
| **Allowed/ignored files** |                                                                                                                                                                                                      |                      |           |
| ALLOW\_FILES\_LIST        | List of comma seperated [minimatch](https://github.com/isaacs/minimatch#minimatch) patterns of allowed files                                                                                         |   '' (all allowed)   |           |
| IGNORE\_FILES\_LIST       | List of comma seperated [minimatch](https://github.com/isaacs/minimatch#minimatch) patterns of ignored files                                                                                         | '' (nothing ignored) |           |
|                           |                                                                                                                                                                                                      |                      |           |
| **Root settings**         |                                                                                                                                                                                                      |                      |           |
| ROOT\_PATH                | Directory to monitor                                                                                                                                                                                 |          \*          |           |
| ROOT\_KEY                 | Root key to identify events related to this directory among all events. Useful when running multiple automate scan on multiple directories. Still mandatory even with only one automate scan running |          \*          |           |
|                           |                                                                                                                                                                                                      |                      |           |
| **Redis**                 |                                                                                                                                                                                                      |                      |           |
| REDIS\_HOST               | Host of Redis server                                                                                                                                                                                 |          \*          |           |
| REDIS\_PORT               | Port of Redis server                                                                                                                                                                                 |          \*          |           |
|                           |                                                                                                                                                                                                      |                      |           |
| **RabbitMQ**              |                                                                                                                                                                                                      |                      |           |
| AMQP\_PROTOCOL            | Protocol for communication with RabbitMQ                                                                                                                                                             |         amqp         |           |
| AMQP\_HOST                | Host of RabbitMQ server                                                                                                                                                                              |          \*          |           |
| AMQP\_PORT                | Port of RabbitMQ server                                                                                                                                                                              |         5672         |           |
| AMQP\_USERNAME            | Username of RabbitMQ server                                                                                                                                                                          |          \*          |           |
| AMQP\_PWD                 | Password of RabbitMQ server                                                                                                                                                                          |          \*          |           |
| AMQP\_QUEUE               | Queue for files events                                                                                                                                                                               |     files\_events    |           |
| AMQP\_EXCHANGE            | Exchange where messages are sent                                                                                                                                                                     |      leav\_core      |           |
| AMQP\_ROUTING\_KEY        | Routing key of messages                                                                                                                                                                              |      files.event     |           |
| AMQP\_TYPE                | Exchange type                                                                                                                                                                                        |        direct        |           |

### Preview generator

Configuration folder: `apps/preview-generator/config`

#### Available settings

_All mandatory settings have no default value and must be provided._

| Environment variable    | Description                                                                    |       Default value      | Mandatory |
| ----------------------- | ------------------------------------------------------------------------------ | :----------------------: | :-------: |
| **Paths**               |                                                                                |                          |           |
| INPUT\_ROOT\_PATH       | Original files path                                                            |            \*            |           |
| OUTPUT\_ROOT\_PATH      | Directory where generated files are stored                                     |            \*            |           |
| ICC\_PATH               | Path of ICC profiles                                                           |            \*            |           |
|                         |                                                                                |                          |           |
| **RabbitMQ**            |                                                                                |                          |           |
| AMQP\_HOST              | Host of RabbitMQ server                                                        |            \*            |           |
| AMQP\_PORT              | Port of RabbitMQ server                                                        |           5672           |           |
| AMQP\_USERNAME          | Username of RabbitMQ server                                                    |            \*            |           |
| AMQP\_PWD               | Password of RabbitMQ server                                                    |            \*            |           |
| AMQP\_TYPE              | Exchange type                                                                  |          direct          |           |
| AMQP\_QUEUE\_IN         | Queue where preview request are read                                           |  files\_preview\_request |           |
| AMQP\_EXCHANGE\_IN      | Exchange where preview request are read                                        |        leav\_core        |           |
| AMQP\_ROUTING\_KEY\_IN  | Routing key of preview requests messages                                       |   files.previewRequest   |           |
| AMQP\_QUEUE\_OUT        | Queue for preview request responses                                            | files\_preview\_response |           |
| AMQP\_EXCHANGE\_OUT     | Exchange where preview response are sent                                       |        leav\_core        |           |
| AMQP\_ROUTING\_KEY\_OUT | Routing key of preview response messages                                       |   files.previewResponse  |           |
|                         |                                                                                |                          |           |
| **Verbose mode**        |                                                                                |                          |           |
| VERBOSE                 | Enable verbose mode. Will log any preview request received and generated files |                          |           |

### Sync scan

Configuration folder: `apps/sync-scan/config`

#### Available settings

_All mandatory settings have no default value and must be provided._

| Env variable               | Description                                                                                                  |     Default value    | Mandatory |
| -------------------------- | ------------------------------------------------------------------------------------------------------------ | :------------------: | :-------: |
|                            |                                                                                                              |                      |           |
| **Allowed/ignored files**  |                                                                                                              |                      |           |
| ALLOW\_FILES\_LIST         | List of comma seperated [minimatch](https://github.com/isaacs/minimatch#minimatch) patterns of allowed files |   '' (all allowed)   |           |
| IGNORE\_FILES\_LIST        | List of comma seperated [minimatch](https://github.com/isaacs/minimatch#minimatch) patterns of ignored files | '' (nothing ignored) |           |
|                            |                                                                                                              |                      |           |
| **GraphQL API (core)**     |                                                                                                              |                      |           |
| GRAPHQL\_URI               | URL of GraphQL API                                                                                           |          \*          |           |
| GRAPHQL\_API\_KEY          | API key for authentication                                                                                   |          \*          |           |
| GRAPHQL\_TREE\_ID          | ID of files tree to compare file system against                                                              |      files\_tree     |           |
|                            |                                                                                                              |                      |           |
| **Files path**             |                                                                                                              |                      |           |
| FILESYSTEM\_ABSOLUTE\_PATH | Directory to check                                                                                           |          \*          |           |
|                            |                                                                                                              |                      |           |
| **RabbitMQ**               |                                                                                                              |                      |           |
| AMQP\_PROTOCOL             | Protocol for communication with RabbitMQ                                                                     |         amqp         |           |
| AMQP\_HOST                 | Host of RabbitMQ server                                                                                      |          \*          |           |
| AMQP\_PORT                 | Port of RabbitMQ server                                                                                      |         5672         |           |
| AMQP\_USERNAME             | Username of RabbitMQ server                                                                                  |          \*          |           |
| AMQP\_PWD                  | Password of RabbitMQ server                                                                                  |          \*          |           |
| AMQP\_EXCHANGE             | Exchange where messages are sent                                                                             |      leav\_core      |           |
| AMQP\_ROUTING\_KEY         | Routing key of messages                                                                                      |      files.event     |           |
| AMQP\_TYPE                 | Exchange type                                                                                                |        direct        |           |
| AMQP\_ROOT\_KEY            | Files root key                                                                                               |        files1        |           |
