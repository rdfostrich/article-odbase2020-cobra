## Problem Statement
{:#problem-statement}

As mentioned in [](#introduction), the hybrid storage solution provided by OSTRICH leads to long delta chains,
which can become problematic for RDF archives with many versions.
Our goal in this work is to investigate if these issues can be alleviated by modifying the delta chain structure.

We formulate our research question as follows:
<q id="research-question">How can we improve the storage of RDF archives under the hybrid storage strategy by modification of the delta chain structure?</q>

Concretely, we start from the hybrid storage approach from OSTRICH,
and we modify its current *unidirectional delta chain* (UDC) into a *bidirectional delta chain* (BDC).
This bidirectional delta chain consists of two smaller delta chains,
with respectively reverse and forward deltas, all pointing to one common intermediary snapshot.
Since this modifications will reduce the maximum length of a delta chain, without requiring more snapshots,
we expect that this will reduce ingestion time, overall storage size, and query execution time for all query atoms.
Based on this, we define the following hypotheses:

1. {:#hypothesis-qualitative-storage}
Storage size is lower for a BDC compared to a UDC.
2. {:#hypothesis-qualitative-ingestion}
In-order ingestion time is lower for a BDC compared to a UDC.
3. {:#hypothesis-qualitative-querying-vm}
VM query execution is faster for a BDC compared to a UDC.
4. {:#hypothesis-qualitative-querying-dm}
DM query execution is faster for a BDC to a UDC.
5. {:#hypothesis-qualitative-querying-vq}
VQ query execution is faster for a BDC to a UDC.