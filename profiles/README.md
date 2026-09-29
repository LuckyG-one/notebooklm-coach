# Domain Coach Profiles

One NotebookLM engine, six specialist profiles.

Profiles:
- recruitment
- peptides
- huberman-health
- investing
- ai-intelligence
- ai-video

Use `profiles/<name>/SKILL.md` as the domain instruction layer and keep the shared ingestion/citation machinery in the repository root.

## Architecture

The root skill owns authentication, YouTube ingestion, NotebookLM querying, transcript import and citation resolution. A profile adds:
1. domain scope;
2. preferred source architecture;
3. evidence hierarchy;
4. query strategy;
5. response contract.

Do not duplicate the Python ingestion scripts per profile.

## Multi-notebook principle

For broad domains, prefer several curated notebooks over one 300-source dump. Ask the most relevant notebook first, then use cross-notebook synthesis when the question spans source classes. Preserve disagreements instead of averaging them away.

## Source manifest

Each profile includes `sources.md`. It is a curation plan, not a claim that those sources are already loaded. Verify channel URLs and source availability before ingestion.
