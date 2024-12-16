# Unhandled JSON Decoding Exception in Dart

This repository demonstrates a common error in Dart when fetching data from an API and parsing JSON: neglecting to handle potential `FormatException`s during JSON decoding.  The original code silently catches any exception during the `http` request, including JSON parsing errors. The solution improves error handling by specifically catching `FormatException` and providing more informative error messages.

## Bug Description
The `fetchData` function fetches data from a remote API. It handles network errors gracefully. However, it lacks explicit handling for cases where the JSON response is malformed or invalid, leading to a `FormatException` during the `jsonDecode` call. This exception is caught by the generic `catch` block, obscuring the specific error.

## Solution
The solution refactors the `catch` block to specifically handle `FormatException`.  It provides a more informative message about the JSON parsing error and allows for better logging and debugging.