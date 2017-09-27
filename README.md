# Proposal for genealogy graph interchange format

Why? GEDCOM lacks genericity, and is intentionally exclusionary.

## What kind of structure are we dealing with?
Excepting instances of time travel, family trees are directed acyclic property graphs, composed of people, marriages, partnerships, guardianships, biological and adoptive parenthood. A number of properties have a temporal component (that is, they apply over a particular timespan), and as such these need to be representable.

A number of generic graph databases exist, which have been adapted for domain specific purposes (Bio4j being the most prominent example). This proposal focuses on the interchange format used by sigma.js (a json file containing a list of nodes, and a list of edges), and by Tinkerpop (GraphSON, wherein nodes contain their edge information).

The proposed format should be available in a flat (List(Node)+List(Edge)) and nested form (List(Node(out: List(Edge), in: List(Edge)))), the former for small scale settings and the latter for compatibility with Tinkerpop.

 Additionally, it is worthwhile to provide this in web native form (JSON) as well as in a high performance, binary form (protobuf).