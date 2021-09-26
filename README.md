# Geo Indexer

Geo Indexer traverse and index points along a route.

Services that are part of Geo Indexer:
- `RouteGuide`
  - `GetFeature`: Obtains the feature at a given position.
  - `ListFeatures`: Obtains the features available within the given region(rectangle).
  - `RecordRoute`: Accepts a stream of points on a route being traversed.
  - `RouteChat`: Accepts a stream of `RouteNote`s sent while a route is being
    traversed. A `RouteNote` is a message sent while at a given point.

## Usage

Execute the following commands from the project root directory:

1. Run the server:

```sh
$ go run server/server.go
```

2. From another terminal, run the client:

```sh
$ go run client/client.go
```

You’ll see output like this:

```sh
2021/09/26 17:35:33 name:"Berkshire Valley Management Area Trail, Jefferson, NJ, USA" location:{latitude:409146138 longitude:-746188906}
2021/09/26 17:35:33 Getting feature for point (0, 0)
2021/09/26 17:35:33 location:{}
2021/09/26 17:35:33 Looking for features within lo:{latitude:400000000 longitude:-750000000} hi:{latitude:420000000 longitude:-730000000}
2021/09/26 17:35:33 Feature: name: "Patriots Path, Mendham, NJ 07945, USA", point:(407838351, -746143763)
2021/09/26 17:35:33 Feature: name: "101 New Jersey 10, Whippany, NJ 07981, USA", point:(408122808, -743999179)
2021/09/26 17:35:33 Feature: name: "U.S. 6, Shohola, PA 18458, USA", point:(413628156, -749015468)
2021/09/26 17:35:33 Feature: name: "5 Conners Road, Kingston, NY 12401, USA", point:(419999544, -740371136)
2021/09/26 17:35:33 Feature: name: "Mid Hudson Psychiatric Center, New Hampton, NY 10958, USA", point:(414008389, -743951297)
  [... snipped ...]
2021/09/26 17:35:33 Traversing 49 points.
2021/09/26 17:35:33 Route summary: point_count:49 distance:416162755
2021/09/26 17:35:33 Got message First message at point(0, 1)
2021/09/26 17:35:33 Got message Second message at point(0, 2)
2021/09/26 17:35:33 Got message Third message at point(0, 3)
2021/09/26 17:35:33 Got message First message at point(0, 1)
2021/09/26 17:35:33 Got message Fourth message at point(0, 1)
2021/09/26 17:35:33 Got message Second message at point(0, 2)
2021/09/26 17:35:33 Got message Fifth message at point(0, 2)
2021/09/26 17:35:33 Got message Third message at point(0, 3)
2021/09/26 17:35:33 Got message Sixth message at point(0, 3)
```
