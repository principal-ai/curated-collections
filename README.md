# Curated Collections

Curated repository collections for Principal AI.

This repository serves as a storage backend for curated collections displayed on the Principal AI website. It uses the same workspace schema as the Alexandria Core Library, enabling the same UI components to work with both user workspaces and curated collections.

## Structure

- `workspaces.json` - Collection definitions (name, description, theme, icon)
- `workspace-memberships.json` - Repository assignments to collections

## Collections

| Collection | Description |
|------------|-------------|
| Featured AI Tools | Open source AI and ML projects worth exploring |
| Developer Productivity | Tools that boost your development workflow |
| React Ecosystem | Essential libraries for React development |
| Rust Projects | High-performance Rust tools and libraries |

## Usage

```typescript
import {
  GitHubFileSystemAdapter,
  WorkspaceManager,
} from '@principal-ai/alexandria-core-library/github';

const adapter = new GitHubFileSystemAdapter({
  owner: 'principal-ai',
  repo: 'curated-collections',
  branch: 'main',
});

await adapter.preloadDirectory('/');

const workspaces = new WorkspaceManager('/', adapter);
const collections = await workspaces.getWorkspaces();
```

## Contributing

To add or modify collections, edit the JSON files and submit a PR.
