# React / MobX / MVVM / Feature-Sliced Design

Apply only in repositories that already use this architecture.

- React components render state and wire events. MobX view models own presentation
  state, actions and lifecycle; services own IO.
- Register services and view models in the existing composition root. Inject
  dependencies through constructors and use the repository's view-model and
  service hooks at React boundaries, such as useViewModel and useService where
  provided. Follow local instructions for the composition path, such as
  src/composition.ts.
- Use the existing async-state primitive, such as ObservableRequest when provided,
  and abort owned requests on disposal.
- Preserve FSD import direction and import slices through their public index.ts.
  Independent modules must not import application layers or the application
  dependency injection container.
- Keep each React component in its own file with a named props interface.
- Use the repository's theme tokens and shared UI primitives (shared/ui/kit where
  provided). Keep product-specific UI above shared infrastructure.
- Keep framework composition outside FSD layers where the repository architecture
  defines it that way. Follow local instructions for exact paths and APIs.

## Structure and verification

- Introduce entities/ and features/ layers when the first slices are needed.
- Treat a reused UI kit and theme as a baseline rather than approved product design;
  check agreed UX before implementing product-specific screens.
- Check React presentation and view-model interactions in a browser. Add domain
  and transport tests when those contracts appear.
- After a SPA build, confirm client output and hashed assets exist and that server
  output is absent when the project is intentionally client-only.
- Check hydration, console errors and the required narrow-viewport layout. Verify
  host SDK behavior with the existing stub, then in the actual host when configured.
  Keep exact routes, SDK calls, version thresholds and expected UI states local.
