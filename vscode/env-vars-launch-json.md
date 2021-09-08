# Set Environment Variables from launch.json

To set an anvironment variable from launch.json, do it like `TEST_VAR` below

```
{
  "version": "0.2.0",
  "configurations": [
    {
      "type": "pwa-node",
      "request": "launch",
      "name": "Launch Program",
      "skipFiles": [
        "<node_internals>/**"
      ],
      "program": "${workspaceFolder}/index.js",
      "env": {
        "TEST_VAR": "foo"
      }
    }
  ]
}
```

Taken from [Stack Overflow 29971572](https://stackoverflow.com/questions/29971572/how-do-i-add-environment-variables-to-launch-json-in-vscode)
