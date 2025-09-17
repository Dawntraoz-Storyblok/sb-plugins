# SB Plugins Monorepo

Prerequisites

- Node (compatible version for the repo)
- pnpm (v10+ recommended)

1. Install workspace dependencies (run from the repository root)

```bash
pnpm install
```

2. Run a command across the whole workspace, use `pnpm -r` or `pnpm --parallel -r` as appropriate.

## Field Plugins

### `ai-tags`

Run the plugin:

```bash
pnpm --filter ai-tags dev
```

Build the plugin:

```bash
pnpm --filter ai-tags build
```

Run tests for the plugin:

```bash
pnpm --filter ai-tags test
```

## Space Plugins

### `ai-content-checker`

> Follow the [space plugin README](/apps/space-plugins/ai-content-checker/README.md) to setup the App and tokens needed.

Run locally:

```bash
pnpm --filter ai-content-checker dev
```

Build the plugin:

```bash
pnpm --filter ai-content-checker build
```

## Demo for "Supercharge Storyblok with Plugins" talk

### Field plugin showcase

1. Overview `FieldPluginResponse`

   Show a `console.log(plugin)` from a [basic field plugin](/apps/field-plugins/ai-tags/src/components/FieldPlugin.vue) to reveal the _type_, _data_, and _actions_ properties.

   Explain the _loading_, _error_, and _loaded_ states for `plugin.type`.

2. Project creation

   Briefly demonstrate `npx @storyblok/field-plugin-cli@latest create` and selecting a template (e.g., JS, Vue 3, or React).

   Highlight the [`src/main.ts`](/apps/field-plugins/ai-tags/src/main.ts) entry point for bootstrapping.

3. Run locally with Sandbox

   Show `pnpm --filter ai-tags dev` and opening the Sandbox URL. Emphasize how the Sandbox emulates the Visual Editor for development.

4. Basic content example (using `createFieldPlugin` or `useFieldPlugin`)

   Show the initial setup using [`useFieldPlugin`](/apps/field-plugins/ai-tags/src/components/FieldPlugin.vue).

   Demonstrate reading content from [`plugin.data.content`](/apps/field-plugins/ai-tags/src/components/FieldPlugin.vue) and updating content using [`plugin.actions.setContent(content + 1)`](/apps/field-plugins/ai-tags/src/components/FieldPlugin.vue) with a button click.

   > Explain the importance of `actions.setContent` for the Visual Editor to acknowledge changes, contrasting it with direct `plugin.data.content` modification.

5. Integrating options

   Show how to create a [_field-plugin.config.json_](/apps/field-plugins/ai-tags/field-plugin.config.json) file with an options array.

   Demonstrate accessing an option like `plugin.data.options.brand` in the code.

6. Advanced interactions

   **Modal window**: Implement a button that calls `plugin.actions.setModalOpen(true)` and conditionally renders content based on `plugin.data.isModalOpen`.

   **Asset Selector**: Show how to call `plugin.actions.selectAsset().then(...)` to open the asset manager and handle the selected asset.

   **AI Prompt** (if time allows): Demonstrate a call to `plugin.actions.promptAI()` with an example action: _'prompt'_ and text to generate content.

7. Deployment walkthrough

   Briefly show `pnpm --filter ai-tags build`.

   Illustrate `npx @storyblok/field-plugin-cli@latest deploy` from `cd apps/field-plugins/ai-tags`, inputting a Personal Access Token, and choosing a scope (e.g., "My plugins").

   Show in Visual Editor: Navigate to a Storyblok space, add a custom field type, select the deployed plugin, and demonstrate its functionality directly within the Visual Editor.
