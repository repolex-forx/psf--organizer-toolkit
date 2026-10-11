# Repolex Knowledge Graph of psf/organizer-toolkit

RDF knowledge graph data for [psf/organizer-toolkit](https://github.com/psf/organizer-toolkit), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download psf/organizer-toolkit
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 661a39b6b07f99cb28b879c541b03a849eef3ea9
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 661a39b6b07f99cb28b879c541b03a849eef3ea9
│           └── chunk-001.nq.gz
├── blob
│   ├── 059fa6c50c21aa7ab0f961f7138bfc9d81525ab9.nq.gz
│   ├── 17e81d461ddea60858bf8faed6c084ca9a1b5bc0.nq.gz
│   ├── 29feec37e9db49e69995e3f517ca98f9065d9f6b.nq.gz
│   ├── 34f0f34e221e086a470c44bb51ee47b7ccc98a42.nq.gz
│   ├── 3766a34c875540de12aa97f348b1c738a0144fa6.nq.gz
│   ├── 411bb88026515113021d6aa4669bfe6b1d48e837.nq.gz
│   ├── 42d285acb3a01d76b811aa1abec21eb6b3142b76.nq.gz
│   ├── 496902c3674e54b138ff08558b3d352b0d140c69.nq.gz
│   ├── 5cc10084caadc9d78174a4e01a33eba3dcd583c7.nq.gz
│   ├── 5f1416eb0435e44d6fdb12ad8e4e20d0719e2b91.nq.gz
│   ├── 6324d401a069f4020efcf0ff07442724b52f47c2.nq.gz
│   ├── 70795346905f205cf9224748e7be65d479fc729e.nq.gz
│   ├── 7ddd746c9617eb7fb0a31ce68c9e2b4489ef9d55.nq.gz
│   ├── 9d105b4ec80747151dcb7a274e0be3588ad39733.nq.gz
│   ├── 9e2128f0b1b59afdc4a3c22b53b2b9d8d7f76c44.nq.gz
│   ├── a307ff728802d7996bf91c05b7cef48c0828a422.nq.gz
│   ├── a4bf14341bdd9b03e04afeadab2a9daf83217112.nq.gz
│   ├── aa8ae118a77057c861f954710958c68719db797b.nq.gz
│   ├── b305cbf2b9a3846fadfeee956662103523dea271.nq.gz
│   ├── b399c95086db2234c07d74f5d6364da0544892c1.nq.gz
│   ├── d17f6eded60e3b96deffdc72248ab800e1293317.nq.gz
│   ├── d99c6077c5e6daeae61296817b4585584a1e7527.nq.gz
│   ├── daaa334caef95e2aa7638ca61682f881b4c99fbc.nq.gz
│   ├── db72ae2226b6e37a126f28c0f1135455bd3893f8.nq.gz
│   ├── e271ecca5aa24b67ef915b0f877678834740639c.nq.gz
│   └── e9619767212413488171c090275b65ab4e1ce968.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 661a39b6b07f99cb28b879c541b03a849eef3ea9.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 34 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[psf/organizer-toolkit](https://github.com/psf/organizer-toolkit)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
