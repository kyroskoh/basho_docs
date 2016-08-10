---
title: "Querying Data in Riak TS"
description: "Querying Data in Riak TS"
menu:
  riak_ts-1.4.0:
    name: "Query Data"
    identifier: "querying_data_riakts"
    weight: 304
    parent: "using"
project: "riak_ts"
project_version: "1.4.0"
toc: true
aliases:
    - /riakts/1.4.0/using/querying/
canonical_link: "https://docs.basho.com/riak/ts/latest/using/querying"
---

{{% note title="WARNING" %}}
When querying, you must ensure the node issuing the query has adequate memory to receive the response. Queries will return rows based on the time span (quanta) specified, if the returning rows do not fit into the memory of the requesting node, the node is likely to fail. 

Any given query consists of subqueries. If a single subquery loads a result that does not fit into memory, an out of memory error will occur on the subquery node and the requesting node will return a timeout error as it waits for the subquery to return.
{{% /note %}}