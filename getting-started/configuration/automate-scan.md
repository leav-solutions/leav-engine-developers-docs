# Automate Scan

{% hint style="info" %}
Configuration folder: `apps/automate-scan/config`
{% endhint %}

_All mandatory settings have no default value and must be provided._

### Allowed/ignored files

| Environment variable | Description                                                                                                  |     Default value    | Mandatory |
| -------------------- | ------------------------------------------------------------------------------------------------------------ | :------------------: | :-------: |
| ALLOW\_FILES\_LIST   | List of comma seperated [minimatch](https://github.com/isaacs/minimatch#minimatch) patterns of allowed files |   '' (all allowed)   |           |
| IGNORE\_FILES\_LIST  | List of comma seperated [minimatch](https://github.com/isaacs/minimatch#minimatch) patterns of ignored files | '' (nothing ignored) |           |

### Root settings

| Environment variable | Description                                                                                                                                                                                          | Default value | Mandatory |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-----------: | :-------: |
| ROOT\_PATH           | Directory to monitor                                                                                                                                                                                 |               |     \*    |
| ROOT\_KEY            | Root key to identify events related to this directory among all events. Useful when running multiple automate scan on multiple directories. Still mandatory even with only one automate scan running |               |     \*    |

### Redis

| Environment variable | Description          | Default value | Mandatory |
| -------------------- | -------------------- | :-----------: | :-------: |
| REDIS\_HOST          | Host of Redis server |               |     \*    |
| REDIS\_PORT          | Port of Redis server |               |     \*    |

### RabbitMQ

| Environment variable | Description                              | Default value | Mandatory |
| -------------------- | ---------------------------------------- | :-----------: | :-------: |
| AMQP\_PROTOCOL       | Protocol for communication with RabbitMQ |      amqp     |           |
| AMQP\_HOST           | Host of RabbitMQ server                  |               |     \*    |
| AMQP\_PORT           | Port of RabbitMQ server                  |      5672     |           |
| AMQP\_USERNAME       | Username of RabbitMQ server              |               |     \*    |
| AMQP\_PWD            | Password of RabbitMQ server              |               |     \*    |
| AMQP\_QUEUE          | Queue for files events                   | files\_events |           |
| AMQP\_EXCHANGE       | Exchange where messages are sent         |   leav\_core  |           |
| AMQP\_ROUTING\_KEY   | Routing key of messages                  |  files.event  |           |
| AMQP\_TYPE           | Exchange type                            |     direct    |           |
