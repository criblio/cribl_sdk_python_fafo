# OutputKinesisMode

In Error mode, PQ writes events to the filesystem only when it detects a non-retryable Destination error. In Backpressure mode, PQ writes events to the filesystem when it detects backpressure from the Destination or when there are non-retryable Destination errors. In Always On mode, PQ always writes events to the filesystem.


## Values

| Name           | Value          |
| -------------- | -------------- |
| `ERROR`        | error          |
| `BACKPRESSURE` | backpressure   |
| `ALWAYS`       | always         |