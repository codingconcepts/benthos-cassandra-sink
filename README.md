# benthos-cassandra-sink
A simple Cassandra sink for Benthos.

## Installation

```
$ go get -u github.com/codingconcepts/benthos-cassandra-sink
```

## Usage

Configure a simple Go application that references this repository and executes its `init` function:

``` go
package main

import (
	"github.com/Jeffail/benthos/v3/lib/service"

	_ "github.com/codingconcepts/benthos-cassandra-sink"
)

func main() {
	service.Run()
}
```

Configure a Benthos configuration file:

``` yaml
input:
    stdout: {}

output:
    type: cassandra
    plugin:
        nodes:
        - "127.0.0.1"
        keyspace: YOUR_KEYSPACE
        table: YOUR_TABLE
        password_authenticator:
            enabled: true
            username: USERNAME
            password: PASSWORD
```

## Thanks

* Adam Wasila for the inspiration from https://github.com/adamwasila/benthos/tree/WIP_output_cassandra
* Ash Jeffs for the help in getting this output to work!