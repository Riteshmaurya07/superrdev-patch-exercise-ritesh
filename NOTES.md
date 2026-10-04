# Patch Notes

## Summary of changes

I made three focused fixes after testing the application locally.

1. Fixed pagination not resetting when the search query or status filter changes. A new search/filter now starts from page 1.
2. Fixed the task search SQL so the archived condition, search condition, and status filter are applied together correctly. The title/description OR conditions are now grouped with parentheses.
3. Removed artificial API latency caused by `Thread.sleep()` in `TaskController`. This was blocking the request thread and adding about 1 second of unnecessary delay for empty searches.

## What I chose not to change

I intentionally did not address other possible improvements or future features because of the exercise timebox. I focused on issues that directly affected correctness and API performance.

## Biggest remaining risk

The API still accepts pagination parameters without explicit validation. Invalid or extreme values could lead to unexpected behavior or unnecessary processing.

## Tools/AI used

I used ChatGPT to help inspect the code, reason about possible bugs, and review the fixes. I reproduced the issues locally, tested the API behavior, measured response times, and made the final code changes myself.