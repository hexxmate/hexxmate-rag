# hexxmate-rag
RAG system for AI Bug Bounty agent with full Knowledge Ingestion pipeline 

## Repo architecture & file structure

> Four-stage pipeline, each stage a separate, independently re-runnable step.
> each stage only depends on the stage before it, never on raw collection again after stage 1.

```
bounty-rag/
├── raw_data/              # untouched originals, never edited after ingestion
│   ├── hacktricks/        # git submodule (see below)
│   ├── payloadsallthethings/  # git submodule
│   ├── portswigger/       # scraped snapshots, dated folders
│   ├── hackerone_curated/ # your manually-picked reports
│   └── obsidian_export/
├── processed/              # cleaned + LLM-extracted structured text, versioned
├── chunks/                 # schema-versioned chunk records (jsonl), regenerable from processed/
├── db/                     # Chroma persistent store — NOT committed to git, rebuild from chunks/
├── scripts/
│   ├── ingest/              # one script per source type
│   ├── extract/              # LLM-assisted structuring step
│   ├── chunk/
│   ├── embed/
│   └── validate/
├── schema/                 # versioned schema definitions + migration scripts
├── eval/                   # retrieval eval query set (query → expected chunk_id)
└── manifest.json           # source URLs, hashes, fetch dates — reproducibility record
```
***

### Embedding model

should be local since it doesn't need any advanced models

### Schema design

Still Working on it ...

### What to study before starting

- Full RAG ingestion pipeline for Agentic AI freecodecamp course is recommended
- link : https://www.youtube.com/watch?v=mHxLXzYjQRE
Still Working on it ...

***




