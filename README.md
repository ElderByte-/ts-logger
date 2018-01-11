
[![CI Status](https://travis-ci.org/ElderByte-/ts-logger.svg?branch=master)](https://travis-ci.org/ElderByte-/ts-logger)
[![npm version](https://badge.fury.io/js/%40elderbyte%2Fts-logger.svg)](https://badge.fury.io/js/%40elderbyte%2Fts-logger)


# TypeScript logger

# Installation

Install via NPM: `npm i --save @elderbyte/ts-logger`


# Usage

```
import {LoggerFactory} from '@elderbyte/ts-logger';

class MyClass {

  private logger = LoggerFactory.getLogger('MyClass');

  public myMethod(): void {
    this.logger.info('You invoked myMethod!');
  }
}

```

# Configuration

Configuration is provided with default values to support out of the box working logging expirience.

Each `LoggerFactory` instance can be configured independently. There is however a global, static default instance and its recommended to use this accross all your projects and libraries. This will allow to configure the logger on a central place (such as your main app).

You can configure the max log level, custom appenders and message formatter. All of these are optional.

```
LoggerFactory.getDefaultConfiguration()
      .withMaxLevel(LogLevel.Trace) // Defaults to Info
      .withAppender(new ConsoleLogAppender()) // Same as default
      .withFormatter(new SimpleMessageFormatter()) // Same as default
```
