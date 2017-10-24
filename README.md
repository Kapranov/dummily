# REST APIs with Elixir with Maru

**Why I love Elixir**

* `|> pattern matching`
* `|> processes`
* `|> Ruby-like`
* `|> mix`

**Maru - Elixir RESTful Framework**

* `|> REST-like API framework`
* `|> inspired by grape (Ruby)`
* `|> running on other web frameworks like Phoenix`
* `|> routing HTTP requests`
* `|> parameter validation and coercoin`
* `|> versioning`

**What does Maru not do?**

* `|> render template`
* `|> database connection`
* `|> plug wrappers like session, header and so on`

**TODO: Add description**

## Installation

Edit `mix.exs`:

```elixir
defmodule Dummily.Mixfile do
  use Mix.Project

  ...

  defp deps do
    [
      {:maru, "~> 0.12.5"},
    ]
  end
end
```

Create and Edit `config/*.exs`:

```elixir
# config/config.exs
use Mix.Config
import_config "#{Mix.env}.exs"

# config/dev.exs
use Mix.Config
config :maru, Dummily.API,
  http: [port: 8880]

# config/prod.exs
use Mix.Config
config :maru, Dummily.API,
  http: [port: 8882]

# config/test.exs
use Mix.Config
config :maru, Dummily.API,
  http: [port: 8881]
```
Run via compile:

```bash
mix do deps.get, compile
mix test
ies -S mix
```

**Users**

* `user_name`
* `email`
* `posts`

```bash
curl "http://localhost:8880/users"
curl "http://localhost:8880/users/1"
curl "http://localhost:8880/users?posts=1"
curl "http://localhost:8880/users?username=Test1"
curl "http://localhost:8880/users?email=test1@example.com"
```

**Dummily**

Dummily is a sample of REST API with Maru.

* `|> Maru Sample Code`
* `|> Returning dummy users data with JSON`
* `|> github.com/kapranov/dummily`

```elixir
case uri do
  "/users/"                         -> All users data
  "/users/1"                        -> ID = 1 user's data
  "/users?username=Test1"           -> including "Test1"
  "/users?email=test1@example.com"  -> including "test1@example.com"
  "/users?posts=1"                  -> including "1"
end
```

**Summary**

* `|> REST-like APIs framework`
* `|> alone or on Phoenix`
* `|> routing, parameter, versioning`
* `|> easy to write REST APIs`
* `|> micro framework`
* `|> e.g. API GW`

### Oct 2017 Oleg G.Kapranov
