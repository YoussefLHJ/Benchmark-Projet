# REST Stack Benchmark

Academic comparison of three Java REST implementations for the same Category–Item domain and PostgreSQL dataset.

## Implementations

| Directory | Implementation |
| --- | --- |
| `WebPerformance` | JAX-RS / Jersey with JPA/Hibernate |
| `WebPerformance - C` | Spring Boot with Spring MVC controllers and JPA/Hibernate |
| `WebPerformance - D` | Spring Boot with Spring Data REST and JPA/Hibernate |

There is no Variant B directory in this repository; the comparison covers the three implementations listed above.

## Methodology

Each implementation includes PostgreSQL setup material, JMeter inputs, Docker Compose files, and Prometheus configuration. The shared domain models categories and items, and the repository includes CSV identifiers plus light and heavy JSON request payloads.

Configuration files are the source of truth for connection-pool settings, indexes, cache behaviour, runtime options, and monitoring setup. Results should be interpreted with their matching scenario and configuration rather than as general framework rankings.

## Monitoring and Results

The repository contains Prometheus configuration and JMX Prometheus agents for the implementations. The detailed report is retained as `BenchMark.pdf` and should be read together with the source configuration and JMeter assets.

## Reproduction

1. Choose an implementation directory.
2. Inspect its `docker-compose.yml`, `init.sql`, `pom.xml`, and JMeter inputs.
3. Start the required PostgreSQL and monitoring services.
4. Build the application with its Maven wrapper.
5. Execute the matching JMeter scenarios and retain raw outputs with the run configuration.

## Attribution

Academic work completed by Youssef Lahjouji and Saad Chihab for the REST web-services performance benchmark.
