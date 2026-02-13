# Arelle Test Engine

[![Arelle Banner](https://arelle.org/arelle/wp-content/themes/platform/images/logo-platform.png)](https://arelle.org/)

## Description

A test engine for [Arelle](https://github.com/Arelle/Arelle).

Improves on Arelle's internal test suite validation process:
- Each testcase is an independent execution of Arelle via the Session API.
- Each execution is representative of the true behavior of Arelle (no test-specific pathways or logic).
- Each execution is easily reproducible (each execution produces runtime options JSON that can be used with `--optionsFile`).
- Each execution produces a dedicated log file.
- Optional multiprocessing.

## Run Unit Tests
```bash
pytest tests/unit_tests
```

## Run Integration Tests
The integration test runner is a wrapper for the test engine.
```
python -m tests.integration_tests.validation.run_conformance_suites --help
options:
  -h, --help            show this help message and exit
  --all                 Select all configured conformance suites
  --build-cache         Use CacheBuilder plugin to build cache from conformance suite usage
  --download-cache      Download and apply pre-built cache package and taxonomy packages
  --download-overwrite  Download (and overwrite) selected conformance suite files
  --download-missing    Download missing selected conformance suite files
  --download-private    Download privately hosted assets (AWS CLI and environment variables required)
  --list                List names of all configured conformance suites
  --log-to-file         Writes logs and results to .txt and .csv files
  --name NAME           Select only conformance suites with given names, comma delimited
  --offline             Run without loading anything from the internet (local files and cache only)
  --public              Select all public conformance suites
  --series              Run shards in series
  --shard SHARD         comma separated list of 0-indexed shards to run
  --shard-count SHARD_COUNT
                        number of shards to split suite into
  --test                Run selected conformance suite tests
  --testcase-filter TESTCASE_FILTER
                        Filter test cases (see --testcaseFilter)
```

To run integration tests through pytest:
```bash
pytest tests/integration_tests/validation/test_conformance_suites.py --offline --log-to-file --download-missing --name=xbrl_dimensions_1_0 
```

## Documentation / Support / Contributing

Check out the README in the [Arelle repository](https://github.com/Arelle/Arelle) for more information.

## License

[Apache License 2.0][license]

[license]: https://arelle.readthedocs.io/en/latest/license.html
