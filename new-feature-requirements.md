# Description

Create interfaces to allow healthcare facilities to rate a worker's performance on a given shift, and potentially block the worker from applying to shifts posted by the healthcare facility in the future.

## Acceptance Criteria

- The new interface to rate a worker's performance should be a REST endpoint that requires the following parameters as part of the JSON request body:
  - `shiftUuid`
  - `workerUuid`
  - `rating`
- The value of `rating` should be an integer between 1 and 5, inclusive.
- The new interface to block a worker from applying to a healthcare facility's future shifts should be a REST endpoint that requires the following parameters as part of the JSON request body:
  - `shiftUuid`
  - `workerUuid`
  - `blockReason`
- Workers who have been blocked from applying to a healthcare facility's shifts should not be able to apply to shifts from the facility that blocked them
