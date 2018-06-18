## Installation

Install with [npm](https://npmjs.org):

```sh
$ npm install just-api
```

>To run just-api, you will need Node.js v7.10.0 or newer.


## Getting Started

```
$ npm install just-api
$ mkdir specs
$ $EDITOR specs/starwars_service.yml # or open with your preferred editor
```

API test specification is written in yaml files, Enter below specification in the yaml file

```yaml
meta:
  name: Star Wars suite
configuration:
  scheme: https
  host: swapi.co
  base_path: /api
specs:
  - name: get "Luke Skywalker" info
    request:
      path: /people/1/
      method: get
    response:
      status_code: 200
      json_data:
        - path: $.name
          value: Luke Skywalker
```

Back in the terminal

```
$ ./node_modules/.bin/just-api

   ✓ get Luke Skywalker info (1516ms)

  Done: specs/suite.yml (Passed)

0 skipped, 0 failed, 1 passed (1 tests)
0 skipped, 0 failed, 1 passed (1 suites)
Duration: 1.6s
```