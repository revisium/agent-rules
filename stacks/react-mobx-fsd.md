# React / MobX / MVVM / Feature-Sliced Design

Apply only in repositories that already use this architecture.

- React components render state and wire events. MobX view models own presentation
  state, actions and lifecycle; services own IO.
- Register services and view models in the existing composition root. Inject
  dependencies through constructors and use the repository's view-model and
  service hooks at React boundaries.
- Use the existing async-state primitive, such as ObservableRequest when provided,
  and abort owned requests on disposal.
- Preserve FSD import direction and import slices through their public index.ts.
  Independent modules must not import application layers or the application
  dependency injection container.
- Keep each React component in its own file with a named props interface.
- Use the repository's theme tokens and shared UI primitives. Keep product-specific
  UI above shared infrastructure.
- Keep framework composition outside FSD layers where the repository architecture
  defines it that way. Follow local instructions for exact paths and APIs.
