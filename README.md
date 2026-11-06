# Repolex Knowledge Graph of lxml/lxml-stubs

RDF knowledge graph data for [lxml/lxml-stubs](https://github.com/lxml/lxml-stubs), parsed by [repolex](https://repolex.ai).

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
rlex download lxml/lxml-stubs
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c6246a1ae5e82a4953ab062f1d7f25f7934f57cb
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c6246a1ae5e82a4953ab062f1d7f25f7934f57cb
│           └── chunk-001.nq.gz
├── blob
│   ├── 04fd89f3ae19d09ac9570d9db1b24d3b500632ca.nq.gz
│   ├── 19185a2a5f2a8d47a88a0c74085b87de83f369e9.nq.gz
│   ├── 30e007ad50ff1e849e6ff00167af52e5f95e118b.nq.gz
│   ├── 36dc5c74e7eb2ca0302f3379dc3b27ba98a691dc.nq.gz
│   ├── 3ddf5dab4c7ade7597b0e9feb174a0ed3784aa4e.nq.gz
│   ├── 411d5933a88a4ccce3b51e72befa8da6799ef799.nq.gz
│   ├── 47bfd98c876c9e906ca4d8ed30e325b3988ccded.nq.gz
│   ├── 57139aef2475a64993a1288a329ed453d7434093.nq.gz
│   ├── 5ebbcff27c3481b62882b15edc59c2d303d161f3.nq.gz
│   ├── 651b2df2e288b0aaeebc27178d413a4846ae0807.nq.gz
│   ├── 671c2e92a15724cdf3c72d04e5bd7411c3df7058.nq.gz
│   ├── 965dd7b826c36b4db2b4d38e3ef9222b75426baa.nq.gz
│   ├── a4efade2ab4b7fa4fce57d057e78bb067e30c8bb.nq.gz
│   ├── d211927a9b3a260a52c4d71f93470d0e3892ca4e.nq.gz
│   ├── da70e201afa99e1d8a0cec0eced23ff139e22661.nq.gz
│   ├── e5833ae4231d68a2cc6878b790199e1d97900b39.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── eb059fa432409ffd1ba2ace439c18d7b7f9ab934.nq.gz
│   └── efea5ce603b476398869c9f7a780200dd7f37dc8.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c6246a1ae5e82a4953ab062f1d7f25f7934f57cb.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 27 files
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

[lxml/lxml-stubs](https://github.com/lxml/lxml-stubs)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
