# Repolex Knowledge Graph of tox-dev/tox-extra

RDF knowledge graph data for [tox-dev/tox-extra](https://github.com/tox-dev/tox-extra), parsed by [repolex](https://repolex.ai).

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
rlex download tox-dev/tox-extra
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9e16b11f7a3e9acdddc5b2bb58f5b3d591882055
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 9e16b11f7a3e9acdddc5b2bb58f5b3d591882055
│           └── chunk-001.nq.gz
├── blob
│   ├── 1893b9fab5ba94ae47d0a33e0edec951f2781fb6.nq.gz
│   ├── 26ec839b6d136ea4d6e41e67c3dd859b786fc41f.nq.gz
│   ├── 2d3b906f58c2fb0a54644e1580bc41a5a4383eb1.nq.gz
│   ├── 325ccef49e02fc184004b35632445bd82ca556ef.nq.gz
│   ├── 32af09d12ba2c954fcf422b4b988b532f2bd5946.nq.gz
│   ├── 354fb450141422d6c3d9dcc9bb55c82ae4d70e66.nq.gz
│   ├── 3714a526cbcf2635f691c7e971c37b4f57afa96f.nq.gz
│   ├── 3deb9c5262bdfb7dfc7fe2635cff93cb8190ee94.nq.gz
│   ├── 3e4e48b0b5fe6b468434d6767749b399319f2da2.nq.gz
│   ├── 52597ada472c458bc69c4b228d8edc4b38a661f1.nq.gz
│   ├── 5960eca1649455c162994447549d7c513d636bde.nq.gz
│   ├── 59f1c0ac09fc528fea91eff359f78eb08f6210ed.nq.gz
│   ├── 5b400b40936a16e9c13f287dd5839c58d418bf42.nq.gz
│   ├── 5e7a4583a95b7433ca28e0f778e9c73115956900.nq.gz
│   ├── 60d4f967a6e08294b64f943c12eb4c7f2b2b1fb8.nq.gz
│   ├── 69cb76019a474330e99666f147ecb85e44de1ce6.nq.gz
│   ├── 731ddce031e4ba2991580d58ac8b86073f12f7c6.nq.gz
│   ├── 77adb89adf64a9b97d798ef97d345b2e3de7a49d.nq.gz
│   ├── 958b0b64781d2a26773dd832a9d8f5023ce1a522.nq.gz
│   ├── a203ea820c0d822b3fab67597c1810ec1b250906.nq.gz
│   ├── b8cb5b5b10fa24bf65fd66d81d39b5903898616b.nq.gz
│   ├── ca0a41e4fc66805902899001f17d0f373fb08bb0.nq.gz
│   ├── ceb23ee4755ae7545a0388ff13ac4638b1b5cfbf.nq.gz
│   ├── d6e510314881faa622ec90c0fe5fa64c92e45d61.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f4834a20a16c1866b2d23a0edd90695a05480f26.nq.gz
│   ├── f7ab61f018e0fa1ed7ba0715f74049a7638d2d8c.nq.gz
│   └── f9afc088a472d9ef4756e6ee9188c81a82c68343.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 9e16b11f7a3e9acdddc5b2bb58f5b3d591882055.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 36 files
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

[tox-dev/tox-extra](https://github.com/tox-dev/tox-extra)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*
