# sqlc-pgx-metrics

![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)

`sqlc-pgx-metrics` is a Go package that offers powerful query time monitoring and logging capabilities for applications using the popular `pgx` and `sqlc` libraries in Golang. If you want to gain insights into the performance of your PostgreSQL database queries and ensure the reliability of your application, this package is a valuable addition to your toolset.

## Features

- **Query Time Monitoring**: Keep a close eye on the execution times of your SQL queries to identify and optimize slow or resource-intensive database operations.

- **Detailed Logging**: Record detailed logs of executed queries, including parameters, timings, and outcomes, which can be invaluable for debugging and performance analysis.

- **Compatible with `pgx` and `sqlc`**: Designed to seamlessly integrate with the `pgx` database driver and the `sqlc` code generation tool, making it a great fit for projects using these technologies.

## Installation

To get started with `sqlc-pgx-metrics`, you can simply use `go get`:

```shell
go get github.com/amirsalarsafaei/sqlc-pgx-metrics@v1.0.0
```

## Usage

To begin using `sqlc-pgx-metrics` in your Go project, follow these basic steps:

1. Import the package:
   ```go
   import "github.com/amirsalarsafaei/sqlc-pgx-metrics/dbtracer"
   ```

2. Before creating connection or connection pool, assign dbTracer in your connection config:

   ### pgx.Conn
   ```go
   connConfig.Tracer = dbtracer.NewDBTracer(
        logger.NewLogger(logrus.New()),
        level,
        prometheus.DefaultRegisterer,
   )
   ```
   ### pgxpool.Pool
   ```go
   poolConfig.ConnConfig.Tracer = dbtracer.NewDBTracer(
       logger.NewLogger(logrus.New()),
       level,
       prometheus.DefaultRegisterer,
   )
   ```

For more information refer to the [example](internal/example)

## License

`sqlc-pgx-metrics` is open-source software licensed under the [MIT License](LICENSE). Feel free to use, modify, and distribute it according to the terms of this license.

## Contributing

We welcome contributions from the community. If you have suggestions, bug reports, or want to contribute to the development of `sqlc-pgx-metrics`, please refer to our [contribution guidelines](CONTRIBUTING.md).

Happy querying and monitoring with `sqlc-pgx-metrics`!