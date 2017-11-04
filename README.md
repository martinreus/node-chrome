# node-chrome

This is a Docker image based on node:6.11.4 which also contains an installation of the latest Chrome Browser, which enables javascript unit tests on a headless Chrome in CI environments.

## notes when using Karma and Docker CI containers
To be able to use Chrome Headless, it is necessary to create a custom ChromeHeadless configuration which disables sandboxing, so that Chrome has sufficient permissions on a Docker Container.

    customLaunchers: {
      ChromeNoSandboxing: {
        base: 'ChromeHeadless',
        flags: [
          '--no-sandbox',
        ]
      }
    },
