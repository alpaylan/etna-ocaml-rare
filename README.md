# etna-ocaml-rare

RARE (random regex / string fuzzing) workload for
[Etna](https://github.com/alpaylan/etna-cli) (OCaml).

Depends on the shared [`etna-ocaml-util`](https://github.com/alpaylan/etna-ocaml-util)
library, vendored here as a git submodule under `./util/`. `etna workload add`
recurses submodules automatically; `steps.json` then runs
`opam install ./util --yes` before the workload build so `util` is available
in the opam switch.

The RARE runner interface differs from the BST/RBT/STLC workloads
(`dune exec RARE -- <strategy> <property> <gen> <out>` and no separate
sampler binary), so the `steps.json` here exposes a single `solve`
capability and omits `sample`.

## Usage

```
etna experiment create my-exp
etna workload add https://github.com/alpaylan/etna-ocaml-rare
```
