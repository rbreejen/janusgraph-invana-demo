# Janusgraph Invana Airroutes Demo
If you are looking to explore & play with the open-source graph database [Janusgraph](https://github.com/JanusGraph/janusgraph) & visualization tool [Invana Studio](https://github.com/invanalabs/invana-studio), you are at the right place! 

By following the instructions below, you will automatically start Janusgraph Server, ScyllaDB (storage), Invana Studio & Invana Engine (visualization). Moreover, it also automatically loads the air-routes and airport dataset provided by [krlawrence](https://github.com/krlawrence/graph/blob/master/sample-data).


## Quickstart

### Usage with Docker-compose

By following the instructions below, you will start all services in individual Docker containers:

```
git clone git@github.com:rbreejen/janusgraph-invana-demo.git
cd janusgraph-invana-demo
docker-compose up
```

### Connecting to Invana Studio & Janusgraph

Navigate to http://localhost:8300/ to access Invana Studio. Then connect to http://localhost:8200/graphql to access the graph.

### Quick queries - cheatsheet

Example queries you can run include:

*Out-going flights from New York John F. Kennedy International Airport (JFK) excluding domestic flights.*
```
g.V().has('code','JFK').outE().inV().has('country',without('US')).path().by(valueMap(true))
```

For more information on Gremlin query syntax & query ideas, see [the excellent Gremlin guide](https://kelvinlawrence.net/book/Gremlin-Graph-Guide.html) by Kelvin Lawrence.


### More tips

1. Test your Gremlin queries against the Gremlin Server! The output you get is exactly what will be visualised in Invana Studio.
2. For performance reasons, it is advisable not to load the full graph in memory when visualizing the graph in Invana Studio.

#### References
- https://kelvinlawrence.net/book/Gremlin-Graph-Guide.html
- https://github.com/krlawrence/graph
- https://docs.janusgraph.org/
- https://github.com/invanalabs/invana-studio
- https://github.com/scylladb/scylla

