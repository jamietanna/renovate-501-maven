# Renovate with Maven Central returns HTTP 501

For https://github.com/renovatebot/renovate/discussions/24498

```sh
# from this repository, run
env RENOVATE_LOG_FILE=debug.log renovate --token $GITHUB_TOKEN jamietanna/renovate-501-maven --dry-run
```

This then results in:

```json
{
  "err": {
    "code": "ERR_NON_2XX_3XX_RESPONSE",
    "message": "Response code 501 (HTTPS Required)",
    "name": "HTTPError",
    "options": {
      "headers": {
        "accept-encoding": "gzip, deflate, br",
        "user-agent": "RenovateBot/36.68.1 (https://github.com/renovatebot/renovate)"
      },
      "hostType": "maven",
      "http2": false,
      "method": "GET",
      "password": "",
      "url": "http://repo1.maven.org/maven2/junit/junit/maven-metadata.xml",
      "username": ""
    },
    "response": {
      "body": "501 HTTPS Required. \nUse https://repo1.maven.org/maven2/\nMore information at https://links.sonatype.com/central/501-https-required\n  ",
      "headers": {
        "accept-ranges": "bytes",
        "connection": "close",
        "content-length": "133",
        "content-type": "text/plain",
        "date": "Mon, 18 Sep 2023 15:47:55 GMT",
        "server": "Varnish",
        "via": "1.1 varnish",
        "x-cache": "MISS",
        "x-cache-hits": "0",
        "x-served-by": "cache-lon420100-LON",
        "x-timer": "S1695052076.625704,VS0,VE0"
      },
      "httpVersion": "1.1",
      "retryCount": 0,
      "statusCode": 501,
      "statusMessage": "HTTPS Required"
    },
    "stack": "HTTPError: Response code 501 (HTTPS Required)\n    at Request.<anonymous> (/usr/lib/node_modules/renovate/node_modules/.pnpm/got@11.8.6/node_modules/got/dist/source/as-promise/index.js:118:42)\n    at processTicksAndRejections (node:internal/process/task_queues:95:5)",
    "timings": {
      "connect": 1695052042614,
      "end": 1695052042635,
      "lookup": 1695052042601,
      "phases": {
        "dns": 23,
        "download": 1,
        "firstByte": 19,
        "request": 1,
        "tcp": 13,
        "total": 57,
        "wait": 0
      },
      "response": 1695052042634,
      "socket": 1695052042578,
      "start": 1695052042578,
      "upload": 1695052042615
    }
  },
  "failedUrl": "http://repo1.maven.org/maven2/junit/junit/maven-metadata.xml",
  "hostname": "TimTheEnchanter",
  "level": 20,
  "logContext": "T4lUm0sSgiKZnFs-MA9Ml",
  "msg": "Temporary error",
  "name": "renovate",
  "pid": 1251408,
  "repository": "jamietanna/renovate-501-maven",
  "time": "2023-09-18T15:47:22.640Z",
  "v": 0
}
```
