As high-speed networks are becoming commonplace, it is increasingly challenging
to prevent the attack attempts at the edge of the Internet. While many
high-performance intrusion detection systems (IDSes) employ dedicated network
processors or special memory to meet the demanding performance requirements, it
often increases the cost and limits functional flexibility. In contrast,
existing softwarebased IDS stacks fail to achieve a high throughput despite
modern hardware innovations such as multicore CPUs, manycore GPUs, and 10 Gbps
network cards that support multiple hardware queues.

We present Kargus, a highly-scalable software-based IDS that exploits the full
potential of commodity computing hardware. First, Kargus batch processes
incoming packets at network cards and achieves up to 40 Gbps input rate even
for minimum-sized packets.  Second, it exploits high processing parallelism by
balancing the pattern matching workloads with multicore CPUs and heterogeneous
GPUs, and benefits from extensive batch processing of multiple packets per each
IDS function call. Third, Kargus adapts its resource usage depending on the
input rate, significantly saving the power in a normal situation. Our
evaluation shows that Kargus on a 12-core machine with two GPUs handles up to
33 Gbps of normal traffic and achieves 9 to 10 Gbps even when all packets
contain attack signatures, a factor of 1.9 to 4.3 performance improvements over
the existing state-of-the-art software IDS. We design Kargus to be compatible
with the most popular software IDS, Snort.