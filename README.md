# httpc

Bindings to Erlang's built in HTTP client, `httpc`.

```rust
import gleam/httpc.{Response, None}
import gleam/http.{Get}
import gleam/expect

pub fn request_test() {
  let response = httpc.request(
    method: Get,
    url: "https://test-api.service.hmrc.gov.uk/hello/world",
    headers: [tuple("accept", "application/vnd.hmrc.1.0+json")],
    body: None,
  )
  expect.equal(response, Ok(Response(
    status: 200,
    headers: [tuple("content-type", "application/json")],
    body: "{\"message\":\"Hello World\"}",
  )))
}
```

## Installation

If [available in Hex](https://hex.pm/docs/publish) this package can be installed
by adding `gleam_httpc` to your `rebar.config` dependencies:

```erlang
{deps, [
    gleam_httpc
]}.
```
