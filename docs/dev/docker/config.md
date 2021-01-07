# Docker Configuration

## Logging

It is standard best practice to send logs of applications running in a Docker container to the [standard output and error streams][1] of the image's OS (`stdout` and `stderr`).  Once you do that, you can view those logs by running the [`docker logs`][2] command.

When applications running in your image are designed to write their logs to a file—rather than to the standard output streams—you can use the file handles below (provided by Docker) to stream log events to `stdout` or `stderr`.

| Type     | File Location     |
|----------|-------------------|
| `STDOUT` | `/proc/self/fd/1` |
| `STDERR` | `/proc/self/fd/2` |


[1]: https://en.wikipedia.org/wiki/Standard_streams
[2]: https://docs.docker.com/config/containers/logging/