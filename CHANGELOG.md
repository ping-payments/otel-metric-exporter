# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

- Export sums, counters and histograms with delta temporality. Each data point was already the change
  during its own interval, but was labelled cumulative, so backends that trust the label miscounted.
  Consecutive delta points now join up (one interval ends where the next starts). Queries and
  dashboards built on the old label may need checking after upgrading.

## [0.3.6] - 2025-04-08

- Fix protobuf encoding of `:logger.report()` events

## [0.3.5] - 2025-04-07

- Fix race conditions registering metrics handlers before `MetricStore` is ready
- Add retries to HTTP POST metric data
