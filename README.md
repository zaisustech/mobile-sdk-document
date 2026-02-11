# Mobile SDK Monorepo

Monorepo for mobile SDK libraries and example applications.

## Structure

```
mobile-sdk/
├── libs/
│   ├── atomic-ui/              # Atomic UI component library (React Native)
│   └── file-system/            # File system utilities
├── apps/
│   ├── example-app/            # Unified example app (Expo dev client)
│   └── docs-site/              # Documentation site (Docusaurus)
└── package.json
```

## Setup

```sh
# Install Bun (if not installed)
curl -fsSL https://bun.sh/install | bash

# Install dependencies
bun install
```

# Note:
  `some troubleshoot with bun install, for install use yarn rest of cmd use bun`


## Development

```sh
# Build libraries
bunx nx build @zaisustech/atomic-ui      # Build atomic-ui library
bunx nx build @zaisustech/file-system    # Build file-system library

# Run applications
bunx nx start example-app                # Start Metro (Expo dev client)
bunx nx ios example-app

bunx nx dev docs-site                    # Start Docusaurus docs (or: bun run docs:dev)

# View dependency graph
bunx nx graph
```

## Libraries

### @zaisustech/atomic-ui

React Native component library with atomic design principles.

**Usage:**
```typescript
import { Button, Input } from '@zaisustech/atomic-ui';

<Button title="Click me" onPress={() => {}} variant="primary" />
<Input label="Email" value={email} onChangeText={setEmail} />
```

### @zaisustech/file-system

File system UI component library for React Native/Expo.

**Usage:**
```typescript
import { FileManagerContainer } from '@zaisustech/file-system';

<FileManagerContainer
  initialPath={FileSystem.documentDirectory}
  onFileSelect={(file) => console.log(file)}
/>
```

## Apps

### example-app

Unified example application showcasing atomic-ui and file-system with Expo dev client.

**Run:**
```sh
# Start Metro bundler
bunx nx start example-app

# Run on iOS
bunx nx run example-app:ios

# Run on Android
bunx nx run example-app:android

# Run on Web
bunx nx run example-app:web
```

### docs-site

Docusaurus documentation site.

**Run:**
```sh
bunx nx dev docs-site
# or
bun run docs:dev
```

## Notes

- Dependencies are hoisted to root `node_modules`
- Workspace packages are linked via `workspace:*`
- Single source of truth for package versions

## License

MIT
