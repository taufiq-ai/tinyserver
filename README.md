# TinyServer

Lightweight HTTP API server using Python's stdlib. Zero dependencies.

## Install

```bash
pip install tinyserver
```

## Usage

```python
from tinyserver import APIServer

server = APIServer(port=8000)

def hello(req):
    return {"message": "Hello World"}

def echo(req, data):
    return {"received": data}

server.add_route('GET', '/hello', hello)
server.add_route('POST', '/echo', echo)

server.run()
```

## Test

```bash
curl http://localhost:8000/hello
curl -X POST http://localhost:8000/echo -d '{"test":"data"}' -H "Content-Type: application/json"
```

---

pypi pkg pubshishing guide: https://packaging.python.org/en/latest/tutorials/packaging-projects/