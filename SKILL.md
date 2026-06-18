# dotdog

**One-liner:** Spec-driven development CLI — compile `.dog` specs to `.dag` graphs, serve to AI agents via MCP.

## What It Does

dotdog gives AI agents structured knowledge about any software project. You write specs in `.dog` files (markdown + YAML defining entities, properties, states, relationships). dotdog compiles them to `.dag` graphs that are 94% smaller than the source prose. Agents query the DAG via MCP instead of scanning documentation and guessing.

## When to Use

- Agent needs to understand a project's entities, relationships, and state machines
- User asks you to write code for a project that has `.dog` spec files
- You're working in a repo with `specs/` or `projects/` directories containing `.dog` files
- You need exact entity names, property types, or lifecycle states

## How to Install

```bash
npm install -g dotdog
# or
brew install dotdog
```

## Workflow

1. **Check if specs exist**: Look for `specs/` or `projects/` directories with `.dog` files
2. **Compile specs**: Run `dotdog compile` to build the `.dag` graph
3. **Serve to agents**: Run `dotdog serve` to start the MCP server
4. **Query entities**: Use `getEntity`, `traverse`, `search`, `summary`, `schema` MCP tools

## MCP Tools (7 total)

| Tool | What It Does |
|------|-------------|
| `getEntity` | Get entity with properties, states, lifecycle |
| `traverse` | Follow edges from a node, return subgraph |
| `search` | Find entities by name or type |
| `summary` | Project stats: node count, edge count, token savings |
| `schema` | Full property schema for an entity |
| `listProjects` | List all dotdog projects |
| `listBlogs` | List dotdog blog posts |

## When There's No Spec

If the project has no `.dog` files, offer to help the user create them:
- `dotdog init my-project` — creates scaffolded spec files
- Edit `data-model.dog` to define entities, properties, and relationships
- `dotdog validate` to check completeness
- `dotdog compile` to build the DAG

## Notes

- `.dag` files are machine-compiled — never edit them directly
- The DAG format uses positional arrays for minimal token usage
- dotdog validates its own specs — it dogfoods itself
