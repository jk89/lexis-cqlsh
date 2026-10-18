# lexis-cqlsh

<table><tr>
<td valign="middle" width="160"><img src="https://raw.githubusercontent.com/jk89/lexisdb/develop/lexis-icon.svg" width="160" height="196" alt="Lexis"></td>
<td valign="middle">

cqlsh for [Lexis](https://github.com/jk89/lexisdb), a fork of ScyllaDB that
replaces the Murmur3 partitioner with byte-ordered partitioning, built on
tablets. In Lexis the token of a partition is an order-preserving encoding of
its partition key.

</td>
</tr></table>

`token()` values print as hex blobs. `COPY TO` and `COPY FROM` split work by
Lexis token ranges, `BEGINTOKEN` and `ENDTOKEN` take hex tokens, and
`SHOW REPLICAS` takes a hex token. Use it with
[lexis-python-driver](https://github.com/jk89/lexis-python-driver).

Docker image, connecting to a Lexis node:

    docker run -it --rm 0x6a6f6e6e79/lexis-cqlsh <host>

## Installation

    pip install git+https://github.com/jk89/lexis-cqlsh

This also installs lexis-python-driver. Or run it from Docker, as above.

## Base and licence

Forked from ScyllaDB's scylla-cqlsh at commit `b09bc79` (after
`v6.0.22-scylla`). Licensed under the Apache License 2.0
([LICENSE.txt](LICENSE.txt)).

The upstream README is kept unchanged in [README_SCYLLA.md](README_SCYLLA.md).