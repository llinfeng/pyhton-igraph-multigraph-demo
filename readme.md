In `deidentified_pub_record.csv`, we provide the raw-record for the network. It
is a collaboration network where authors are identified by SubjectID.

In each row, we record one publication by an author, where the `edge_ID` is a
masked string that was mapped from the DOI for the original publication record.

Towards the end of `Demo-subgraph-with-2-implementations.ipynb`, we demonstrate
that different `implementation` parameters shall give raise to different
subgraph. 
```
i_giant_graph = g.subgraph(igiant_component, implementation='copy_and_delete')
i_giant_graph.summary()
> 'IGRAPH UN-- 2004 4533 -- \n+ attr: name (v), edgeid (e)'
i_giant_bad = g.subgraph(igiant_component, implementation='create_from_scratch')
i_giant_bad.summary()
> 'IGRAPH UN-- 2004 4755 -- \n+ attr: name (v), edgeid (e)'
```
By the raw record, there are 4533 edges in the giant component, agreeing with
the `copy_and_delete` option for `implementation=` parameter.
