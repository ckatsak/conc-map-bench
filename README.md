# conc-map-bench

conc-map-bench uses the bustle benchmarking harness. This is a port of the well regarded libcuckoo benchmark.

## Workloads

The benchmark measures performance under varying load conditions. This is done
because a map suitable for one workload may not be suitable for another.

### Read Heavy

A read heavy model with few inserts, removals and updates. Models caching of data in places such as webservers and disk page caches.
```
read   98%
insert  1%
remove  1%
update  0%
```

### Exchange

Insert and remove heavy model that replicates a scenario where the map is used to exchange data.
```
read    10%
insert  40%
remove  40%
update  10%
```

### Rapid Grow

An insert heavy model that replicates load in a scenario where the map is used to gather large amounts of data under a short burst.
```
read    5%
insert 80%
remove  5%
update 10%
```

### Reads and Updates

TODO
```
read   47%
insert  1%
remove  1%
update 47%
```

## How to run it?

```sh
mv results results.bk
./scripts/bench.bash
./scripts/plot.bash
```

## Results

- Intel(R) Xeon(R) Silver 4314 CPU @ 2.40GHz
  * SMT off
  * using cores of a single NUMA node
  * all allocations on that NUMA node
- Debian trixie (testing)

See the `results_nosmt/` directory.

### Read Heavy (std hasher)
| | |
:-------------------------:|:-------------------------:
![](results_nosmt/ReadHeavy.std.throughput.svg) | ![](results_nosmt/ReadHeavy.std.latency.svg)

### Exchange (std hasher)
| | |
:-------------------------:|:-------------------------:
![](results_nosmt/Exchange.std.throughput.svg) | ![](results_nosmt/Exchange.std.latency.svg)

### Rapid Grow (std hasher)
| | |
:-------------------------:|:-------------------------:
![](results_nosmt/RapidGrow.std.throughput.svg) | ![](results_nosmt/RapidGrow.std.latency.svg)

### Reads and Updates (std hasher)
| | |
:-------------------------:|:-------------------------:
![](results_nosmt/ReadsAndUpdates.std.throughput.svg) | ![](results_nosmt/ReadsAndUpdates.std.latency.svg)

### Read Heavy (ahash)
| | |
:-------------------------:|:-------------------------:
![](results_nosmt/ReadHeavy.ahash.throughput.svg) | ![](results_nosmt/ReadHeavy.ahash.latency.svg)

### Exchange (ahash)
| | |
:-------------------------:|:-------------------------:
![](results_nosmt/Exchange.ahash.throughput.svg) | ![](results_nosmt/Exchange.ahash.latency.svg)

### Rapid Grow (ahash)
| | |
:-------------------------:|:-------------------------:
![](results_nosmt/RapidGrow.ahash.throughput.svg) | ![](results_nosmt/RapidGrow.ahash.latency.svg)

### Reads and Updates (ahash)
| | |
:-------------------------:|:-------------------------:
![](results_nosmt/ReadsAndUpdates.ahash.throughput.svg) | ![](results_nosmt/ReadsAndUpdates.ahash.latency.svg)

### Read Heavy (gxhash)
| | |
:-------------------------:|:-------------------------:
![](results_nosmt/ReadHeavy.gxhash.throughput.svg) | ![](results_nosmt/ReadHeavy.gxhash.latency.svg)

### Exchange (gxhash)
| | |
:-------------------------:|:-------------------------:
![](results_nosmt/Exchange.gxhash.throughput.svg) | ![](results_nosmt/Exchange.gxhash.latency.svg)

### Rapid Grow (gxhash)
| | |
:-------------------------:|:-------------------------:
![](results_nosmt/RapidGrow.gxhash.throughput.svg) | ![](results_nosmt/RapidGrow.gxhash.latency.svg)

### Reads and Updates (gxhash)
| | |
:-------------------------:|:-------------------------:
![](results_nosmt/ReadsAndUpdates.gxhash.throughput.svg) | ![](results_nosmt/ReadsAndUpdates.gxhash.latency.svg)

### Read Heavy (foldhash)
| | |
:-------------------------:|:-------------------------:
![](results_nosmt/ReadHeavy.foldhash.throughput.svg) | ![](results_nosmt/ReadHeavy.foldhash.latency.svg)

### Exchange (foldhash)
| | |
:-------------------------:|:-------------------------:
![](results_nosmt/Exchange.foldhash.throughput.svg) | ![](results_nosmt/Exchange.foldhash.latency.svg)

### Rapid Grow (foldhash)
| | |
:-------------------------:|:-------------------------:
![](results_nosmt/RapidGrow.foldhash.throughput.svg) | ![](results_nosmt/RapidGrow.foldhash.latency.svg)

### Reads and Updates (foldhash)
| | |
:-------------------------:|:-------------------------:
![](results_nosmt/ReadsAndUpdates.foldhash.throughput.svg) | ![](results_nosmt/ReadsAndUpdates.foldhash.latency.svg)
