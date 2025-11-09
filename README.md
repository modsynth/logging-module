# Logging Module

> Structured logging module for Go using Zap

Part of the [Modsynth](https://github.com/modsynth) ecosystem.

## Features

- Structured logging with Zap
- Multiple log levels (debug, info, warn, error, fatal)
- JSON and console output formats
- High performance

## Installation

```bash
go get github.com/modsynth/logging-module
```

## Quick Start

```go
package main

import (
    "github.com/modsynth/logging-module"
    "go.uber.org/zap"
)

func main() {
    // Create logger
    logger, _ := logging.New(&logging.Config{
        Level:  "info",
        Format: "json",
    })
    defer logger.Sync()

    // Log messages
    logger.Info("Application started")
    logger.Debug("Debug message", zap.String("key", "value"))
    logger.Error("Error occurred", zap.Error(err))

    // With context
    userLogger := logger.With(zap.String("user_id", "123"))
    userLogger.Info("User action")
}
```

## Version

Current version: `v0.1.0`

## License

MIT
