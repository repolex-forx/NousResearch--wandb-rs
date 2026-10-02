# Repolex Knowledge Graph of NousResearch/wandb-rs

RDF knowledge graph data for [NousResearch/wandb-rs](https://github.com/NousResearch/wandb-rs), parsed by [repolex](https://repolex.ai).

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
rlex download NousResearch/wandb-rs
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c5f552464f13d56a5abd73c2dfb88b193e991d4e
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── c5f552464f13d56a5abd73c2dfb88b193e991d4e.nq.gz
│   └── repolex
│       └── c5f552464f13d56a5abd73c2dfb88b193e991d4e
│           └── chunk-001.nq.gz
├── blob
│   ├── 002cb1a41c645a97d278a96f492505abfbdf52d1.nq.gz
│   ├── 01705cecfa2572ff487c05a0258ce37b518ddbf3.nq.gz
│   ├── 0297f3c775d445ee2eb6084521607ab7c88af516.nq.gz
│   ├── 03cf2cdf5630aba3b64bdb178462e5a002919c55.nq.gz
│   ├── 05011925f1d55d914f52fde9ac9057b123367d61.nq.gz
│   ├── 0db06cdae1154d7700e5192cbb4c0f1e9c56d481.nq.gz
│   ├── 155d80cdfc20ae5c543169a893a1dbb8b4f70850.nq.gz
│   ├── 1c8aae8919e0eb64bc8943f838aacda3809ba934.nq.gz
│   ├── 2fdb5063742f8e9d6eefcd33a3169ca27983f165.nq.gz
│   ├── 3132016ca7a97cb3eab1ab0e699e4e3e879b0593.nq.gz
│   ├── 3550a30f2de389e537ee40ca5e64a77dc185c79b.nq.gz
│   ├── 48868719c9ecff3f57f158d022d5d9aa723b6832.nq.gz
│   ├── 48d97aa55a5fb463f33a268dc33a56beb2497400.nq.gz
│   ├── 4e4e0bc3a3713d2c47a9b41004847af8b7a6614a.nq.gz
│   ├── 5016e4604fbf82e2732a7a7adea57a114da0add7.nq.gz
│   ├── 554ee6c07da8240d88b0aee40f04f0a02c56ac43.nq.gz
│   ├── 5a61589d5922fee28bd5e3189a052a00c833e8bc.nq.gz
│   ├── 5b557bbab424a52d5f0910a781005999b9c90877.nq.gz
│   ├── 6479d1301ce93b9af3eac327be46c45df08c9dea.nq.gz
│   ├── 6612e02d1e22cbc4269ce9b673983107d5efbe13.nq.gz
│   ├── 6aac7cf001289d5b981a6ea7e4c50cd52d7d76ed.nq.gz
│   ├── 6bd7ce711e5984282ef3ff7f4974b337bdfbff11.nq.gz
│   ├── 6cac0662a94c638e1d880f92f7890de04fcd7848.nq.gz
│   ├── 77ccafff551b58ed6f1e0c24dca3b2ff50e26cba.nq.gz
│   ├── 8480d497776df9d705874d63fc2f07fff2b9e3de.nq.gz
│   ├── 84e9d19c213bcf8f438442bba2f80b81754518da.nq.gz
│   ├── 9a248c6fc73df287978036bf19861ade26cd5bcf.nq.gz
│   ├── a07070db5fecc3e3523a27584ff5f21a990c0dcd.nq.gz
│   ├── b9a8d21daa0724bbdfe3cac692e45af21929c781.nq.gz
│   ├── caf0ce5b363b6dfbccc805a8a1fcfa13387d7972.nq.gz
│   ├── d0da40500febc100b86fc9dc7c1aa5d61f813299.nq.gz
│   ├── d760bd94408a9e75ee58b95092b6462439efcc88.nq.gz
│   ├── d7b30255f4d078e4b04f8f008cb64a79758bf50b.nq.gz
│   ├── e001440376ecc570590962a3063119e818d04b7c.nq.gz
│   ├── ee25fba7f98eab8c6085e0452382acc556940ae6.nq.gz
│   ├── f037c50cdd7b07cbc3967ebbdd855dadfe1e9217.nq.gz
│   ├── f6568182ef21bab9a7fbd5417968e937db3e274f.nq.gz
│   └── f70f86b6f2247fda00a2a4518bb543268dfc09e0.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── c5f552464f13d56a5abd73c2dfb88b193e991d4e.nq.gz
├── filetree
│   └── c5f552464f13d56a5abd73c2dfb88b193e991d4e.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 47 files
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

[NousResearch/wandb-rs](https://github.com/NousResearch/wandb-rs)

---
*Parsed on 2026-10-02 by [repolex](https://repolex.ai)*
