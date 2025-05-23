Sentry integrations that have subscribed to error webhooks can receive information about an error being created.

## Sentry-Hook-Resource Header

`'Sentry-Hook-Resource': 'error'`

## Attributes

### action

- type: string
- description: only option currently is `created`

### data['error']

- type: object
- description: the error that was created

### data['error']['url']

- type: string
- description: the api url for the error

### data['error']['web_url']

- type: string
- description: the web url for the error

### data['error']['issue_url']

- type: string
- description: the api url for the associated issue

### data['event']['issue_id']

- type: string
- description: the id of the issue

If you've set up user identification you can find the user attributes under `data['error']['user']`.

## Payload

```json
{
  "action": "created",
  "actor": {
    "id": "sentry",
    "name": "Sentry",
    "type": "application"
  },
  "data": {
    "error": {
      "_ref": 1293919,
      "_ref_version": 2,
      "contexts": {
        "browser": {
          "name": "Chrome",
          "type": "browser",
          "version": "75.0.3770"
        },
        "os": {
          "name": "Mac OS X",
          "type": "os",
          "version": "10.14.0"
        }
      },
      "culprit": "?(runner)",
      "datetime": "2019-08-19T20:58:37.391000Z",
      "dist": null,
      "event_id": "bb78c1407cea4519aa397afc059c793d",
      "exception": {
        "values": [
          {
            "mechanism": {
              "data": {
                "message": "blooopy is not defined",
                "mode": "stack",
                "name": "ReferenceError"
              },
              "description": null,
              "handled": false,
              "help_link": null,
              "meta": null,
              "synthetic": null,
              "type": "onerror"
            },
            "stacktrace": {
              "frames": [
                {
                  "abs_path": "https://null.jsbin.com/runner",
                  "colno": 5,
                  "context_line": "<meta charset=utf-8>",
                  "data": {
                    "orig_in_app": 1
                  },
                  "errors": null,
                  "filename": "/runner",
                  "function": null,
                  "image_addr": null,
                  "in_app": false,
                  "instruction_addr": null,
                  "lineno": 3,
                  "module": "runner",
                  "package": null,
                  "platform": null,
                  "post_context": [
                    "<title>JS Bin Runner</title>",
                    "",
                    "<style type=\"text/css\">",
                    "  body {",
                    "    margin: 0;"
                  ],
                  "pre_context": ["<!doctype html>", "<html>"],
                  "raw_function": null,
                  "symbol": null,
                  "symbol_addr": null,
                  "trust": null,
                  "vars": null
                }
              ]
            },
            "type": "ReferenceError",
            "value": "blooopy is not defined"
          }
        ]
      },
      "fingerprint": ["{{ default }}"],
      "grouping_config": {
        "enhancements": "eJybzDhxY05qemJypZWRgaGlroGxrqHRBABbEwcC",
        "id": "legacy:2019-03-12"
      },
      "hashes": ["07d2da329989f6cd310eb5f1c5e828a4"],
      "issue_url": "https://sentry.io/api/0/issues/1170820242/",
      "issue_id": "1170820242",
      "key_id": "667532",
      "level": "error",
      "location": "/runner",
      "logger": "",
      "message": "",
      "metadata": {
        "filename": "/runner",
        "type": "ReferenceError",
        "value": "blooopy is not defined"
      },
      "platform": "javascript",
      "project": 1,
      "received": 1566248317.391,
      "release": null,
      "request": {
        "cookies": null,
        "data": null,
        "env": null,
        "fragment": null,
        "headers": [
          [
            "User-Agent",
            "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_0) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3770.100 Safari/537.36"
          ]
        ],
        "inferred_content_type": null,
        "method": null,
        "query_string": [],
        "url": "https://null.jsbin.com/runner"
      },
      "sdk": {
        "integrations": [
          "InboundFilters",
          "FunctionToString",
          "BrowserApiErrors",
          "Breadcrumbs",
          "GlobalHandlers",
          "LinkedErrors",
          "HttpContext"
        ],
        "name": "sentry.javascript.browser",
        "packages": [
          {
            "name": "npm:@sentry/browser",
            "version": "5.5.0"
          }
        ],
        "version": "5.5.0"
      },
      "tags": [
        ["browser", "Chrome 75.0.3770"],
        ["browser.name", "Chrome"],
        ["handled", "no"],
        ["level", "error"],
        ["mechanism", "onerror"],
        ["os", "Mac OS X 10.14.0"],
        ["os.name", "Mac OS X"],
        ["user", "ip:162.217.75.90"],
        ["url", "https://null.jsbin.com/runner"]
      ],
      "time_spent": null,
      "timestamp": 1566248317.391,
      "title": "ReferenceError: blooopy is not defined",
      "type": "error",
      "url": "https://sentry.io/api/0/projects/test-org/front-end/events/bb78c1407cea4519aa397afc059c793d/",
      "user": {
        "ip_address": "162.218.85.90"
      },
      "version": "7",
      "web_url": "https://sentry.io/organizations/test-org/issues/1170820242/events/bb78c1407cea4519aa397afc059c793d/"
    }
  },
  "installation": {
    "uuid": "a8e5d37a-696c-4c54-adb5-b3f28d64c7de"
  }
}
```
