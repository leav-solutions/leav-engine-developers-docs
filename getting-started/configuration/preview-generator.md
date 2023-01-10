# Preview Generator

{% hint style="info" %}
Configuration folder: `apps/preview-generator/config`
{% endhint %}

_All mandatory settings have no default value and must be provided._

### Paths

| Environment variable | Description                                | Default value | Mandatory |
| -------------------- | ------------------------------------------ | :-----------: | :-------: |
| INPUT\_ROOT\_PATH    | Original files path                        |               |     \*    |
| OUTPUT\_ROOT\_PATH   | Directory where generated files are stored |               |     \*    |
| ICC\_PATH            | Path of ICC profiles                       |               |     \*    |

### RabbitMQ

| Environment variable    | Description                              |       Default value      | Mandatory |
| ----------------------- | ---------------------------------------- | :----------------------: | :-------: |
| AMQP\_HOST              | Host of RabbitMQ server                  |                          |     \*    |
| AMQP\_PORT              | Port of RabbitMQ server                  |           5672           |           |
| AMQP\_USERNAME          | Username of RabbitMQ server              |                          |     \*    |
| AMQP\_PWD               | Password of RabbitMQ server              |                          |     \*    |
| AMQP\_TYPE              | Exchange type                            |          direct          |           |
| AMQP\_QUEUE\_IN         | Queue where preview request are read     |  files\_preview\_request |           |
| AMQP\_EXCHANGE\_IN      | Exchange where preview request are read  |        leav\_core        |           |
| AMQP\_ROUTING\_KEY\_IN  | Routing key of preview requests messages |   files.previewRequest   |           |
| AMQP\_QUEUE\_OUT        | Queue for preview request responses      | files\_preview\_response |           |
| AMQP\_EXCHANGE\_OUT     | Exchange where preview response are sent |        leav\_core        |           |
| AMQP\_ROUTING\_KEY\_OUT | Routing key of preview response messages |   files.previewResponse  |           |

### Verbose mode

| Environment variable | Description                                                                    | Default value | Mandatory |
| -------------------- | ------------------------------------------------------------------------------ | :-----------: | :-------: |
| VERBOSE              | Enable verbose mode. Will log any preview request received and generated files |               |           |
