# Python client for [HashiCorp Consul](http://www.consul.io/)

## PyPi
This code is avaliable at PyPI as [consul-reborn](https://pypi.org/project/consul-reborn/).

## Creators
Original code belongs to [Andy Gayton](https://github.com/cablehead).
And fork with community patches belongs to [Carlos](https://github.com/nzlosh).

## Disclamer
I don't like how it has been written but have no time for full refactoring, so I just fix issues that I crossed by.
I do not fix CI or tests, sorry for that.

## Status
I'm using some of its function in production, so it's not a complete junk.

## Documentation
[Original Library Documentation](https://python-consul.readthedocs.io)

## Example
``` {.sourceCode .python}
import consul

c = consul.Consul()

# poll a key for updates
index = None
while True:
    index, data = c.kv.get('foo', index=index)
    print data['Value']

# in another process
c.kv.put('foo', 'bar')
```

Alternatively you can create a client from the same [environment
variables](https://www.consul.io/docs/commands/index.html#environment-variables) that the consul command line client uses. e.g.
CONSUL\_HTTP\_ADDR, CONSUL\_HTTP\_TOKEN.

``` {.sourceCode .python}
import consul

c = consul.Consul.from_env()

c.agent.self()
```

## Installation
```
pip3 install consul-reborn
```
