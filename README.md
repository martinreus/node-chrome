# node-chrome

This is a Docker image based on node which also contains an installation of the latest Chrome Browser, which enables javascript unit tests on a headless Chrome in CI environments.

## Using Karma and Docker Container in CI tests
To be able to use Chrome Headless, it is necessary to create a custom ChromeHeadless in karma.conf.js configuration which disables sandboxing, so that Chrome has sufficient permissions on a Docker Container.

    customLaunchers: {
      ChromeNoSandboxing: {
        base: 'ChromeHeadless',
        flags: [
          '--no-sandbox',
        ]
      }
    },

## Docker Hub Image
https://hub.docker.com/r/martinreus/node-chrome/
