# Asynchronous Batch Request Function

## Overview
The `sendRequests` function is an asynchronous JavaScript function designed to send multiple POST requests to a specified endpoint with a set of payloads. It handles the requests concurrently and returns a structured response indicating the success or failure of each request.

## Function Definition
```javascript
async function sendRequests(endpoint, payloads) {
  const promises = payloads.map((payload) => {
    return fetch(endpoint, {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify(payload),
    })
      .then((response) => {
        if (!response.ok) {
          throw new Error(`Request failed with status ${response.status}`);
        }
        return response.json();
      })
      .catch((error) => {
        return { error: error.message };
      });
  });

  const results = await Promise.allSettled(promises);

  return results.map((result) => {
    if (result.status === "fulfilled") {
      return { success: true, data: result.value };
    } else {
      return { success: false, error: result.reason };
    }
  });
}
