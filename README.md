# zap logger adapter
[![Build Status](https://travis-ci.org/clevergo/log-zap.svg?branch=master)](https://travis-ci.org/clevergo/log-zap)
[![Coverage Status](https://coveralls.io/repos/github/clevergo/log-zap/badge.svg?branch=master)](https://coveralls.io/github/clevergo/log-zap?branch=master) 
[![GoDoc](https://img.shields.io/badge/godoc-reference-blue)](https://pkg.go.dev/github.com/clevergo/log-zap)
[![Go Report Card](https://goreportcard.com/badge/github.com/clevergo/log-zap)](https://goreportcard.com/report/github.com/clevergo/log-zap)
[![Release](https://img.shields.io/github/release/clevergo/log-zap.svg?style=flat-square)](https://github.com/clevergo/log-zap/releases)

This package is an adapter of [universal logger interface](https://github.com/clevergo/log) for [zap](https://github.com/sirupsen/logrus).

## Usage

```go
import (
    "github.com/clevergo/log"
    zapadapter "github.com/clevergo/log-zap"
    "go.uber.org/zap"
)

var logger log.Logger

func main() {
    zapLogger, err := zap.NewDevelopment(zap.AddCallerSkip(1))
    if err != nil {
        panic(err)
    }
    logger := New(zapLogger.Sugar())
    logger.Debug("debug msg")
    // ...
}
```
