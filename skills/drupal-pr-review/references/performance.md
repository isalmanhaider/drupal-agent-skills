# Performance and scalability checks

Use these when the pull request changes queries, loops over entities,
remote calls, rendering or caching.

## Check

- N+1 database queries and queries inside loops
- Repeated entity loading where `loadMultiple()` would do
- Missing pagination and unbounded queries
- Inefficient joins, and missing or unsuitable indexes
- Expensive render operations
- Excessive memory use and large file processing
- Repeated remote API calls, and synchronous blocking calls during a page
  request
- Cache bypass and incorrect cache invalidation
- Unnecessary database writes

## For each performance finding, explain

- the expensive operation;
- how often it runs;
- the conditions that make it worse;
- the likely production impact;
- a practical alternative.

Do not call a change slow just because it contains a loop or a database
query.
