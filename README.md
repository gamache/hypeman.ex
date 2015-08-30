# Hypeman.ex

An Elixir client library for hypermedia APIs.

First in a series of "Hypeman" clients, intended to present a
consistent interface to hypermedia APIs across platforms.

## Totally Made-Up Examples

```elixir
api = Hypeman.link("https://api.example.com/")
      |> Hypeman.Config.basic_auth("username", "password")
      |> Hypeman.Config.body_format("application/json")
      |> Hypeman.get
#=> %Hypeman.Resource{...}

user = api.links['example:user']
       |> Hypeman.where(user_id: 22)
       |> Hypeman.get
#=> %Hypeman.Resource{...}

user.attributes['email']  #=> "johndoe@example.com"

users = api.links['example:users']
        |> Hypeman.where(email: "janedoe@example.com")
        |> Hypeman.post

Enum.first(users.resources) #=> %Hypeman.Resource{...}

```

## TODO

TL;DR: basically everything

## Authorship and License

Copyright 2015 Pete Gamache.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

