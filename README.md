# Vue Flow starter (Vite + TypeScript)

This template is a starting point for building with Vue Flow. Use it as a base for your own Vue Flow applications, or for small experiments and bug reports.

## Getting up and running

Install the dependencies:

```bash
pnpm install
```

Use Node.js 20.19+ or 22.12+ and pnpm. Start the Vite development server:

```bash
pnpm dev
```

Changes you make to the code will be reflected in the browser while the server is running. To create a production build, run `pnpm build`.

The starter includes Vue 3, TypeScript, Vue Flow, Vite, and Oxlint. Run `pnpm lint` to check the code and `pnpm preview` to preview a production build. It also includes examples of a custom node and a custom edge.

## Things to try

- Customize the existing node in `src/CustomNode.vue` or create a new Vue component and register it using a node slot in `src/App.vue`.
- Customize the edge in `src/CustomEdge.vue` or create an edge of your own.
- Change how things look by [theming Vue Flow](https://vueflow.dev/learn/customization/theming).
- Add a layouting library to [position your nodes automatically](https://vueflow.dev/learn/layouting/overview).

## Resources

- [Vue Flow documentation](https://vueflow.dev/)
- [Quick start](https://vueflow.dev/learn)
- [Custom nodes](https://vueflow.dev/learn/customization/custom-nodes)
- [Layouting](https://vueflow.dev/learn/layouting/overview)
