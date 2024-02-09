# Database integration tests

Some repository classes have more complex queries that may
require some testing to verify that they're working correctly.

## 1. Acceptance Criteria

There should be tests (happy and unhappy cases) for every non-trivial query in `ScheduleRepository`.
The non-trivial queries are those methods that are explicitly specified in the interface.

## 2. Implementation Details

You'll have to rely on your previous testing experience, consult the provided references
and do your own research to figure out how to best test these queries.