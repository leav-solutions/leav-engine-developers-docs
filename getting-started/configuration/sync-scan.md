# Sync Scan

{% hint style="info" %}
Configuration folder: `apps/sync-scan/config`
{% endhint %}

_All mandatory settings have no default value and must be provided._

### Allowed/ignored files

| Env variable        | Description                                                                                                  |     Default value    | Mandatory |
| ------------------- | ------------------------------------------------------------------------------------------------------------ | :------------------: | :-------: |
| ALLOW\_FILES\_LIST  | List of comma seperated [minimatch](https://github.com/isaacs/minimatch#minimatch) patterns of allowed files |   '' (all allowed)   |           |
| IGNORE\_FILES\_LIST | List of comma seperated [minimatch](https://github.com/isaacs/minimatch#minimatch) patterns of ignored files | '' (nothing ignored) |           |

### GraphQL API (core)

| Env variable      | Description                                     | Default value | Mandatory |
| ----------------- | ----------------------------------------------- | :-----------: | :-------: |
| GRAPHQL\_URI      | URL of GraphQL API                              |               |     \*    |
| GRAPHQL\_API\_KEY | API key for authentication                      |               |     \*    |
| GRAPHQL\_TREE\_ID | ID of files tree to compare file system against |  files\_tree  |           |

### Files path

| Env variable               | Description        | Default value | Mandatory |
| -------------------------- | ------------------ | :-----------: | :-------: |
| FILESYSTEM\_ABSOLUTE\_PATH | Directory to check |               |     \*    |

### RabbitMQ

| Env variable       | Description                              | Default value | Mandatory |
| ------------------ | ---------------------------------------- | :-----------: | :-------: |
| AMQP\_PROTOCOL     | Protocol for communication with RabbitMQ |      amqp     |           |
| AMQP\_HOST         | Host of RabbitMQ server                  |               |     \*    |
| AMQP\_PORT         | Port of RabbitMQ server                  |      5672     |           |
| AMQP\_USERNAME     | Username of RabbitMQ server              |               |     \*    |
| AMQP\_PWD          | Password of RabbitMQ server              |               |     \*    |
| AMQP\_EXCHANGE     | Exchange where messages are sent         |   leav\_core  |           |
| AMQP\_ROUTING\_KEY | Routing key of messages                  |  files.event  |           |
| AMQP\_TYPE         | Exchange type                            |     direct    |           |
| AMQP\_ROOT\_KEY    | Files root key                           |     files1    |           |

