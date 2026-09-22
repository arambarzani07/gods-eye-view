# iOS IPA build

The repository includes a GitHub Actions workflow that builds the Vite application, wraps the generated `dist` directory with Capacitor iOS, compiles it with Xcode without code signing, and uploads `GodsEyeView-unsigned.ipa` as a workflow artifact.

The IPA is intended for sideloading after signing with the installer's Apple certificate/profile.

## Important runtime note

The packaged web assets run locally in WKWebView. Browser-direct public sources can continue to work, but features that depend on this repository's Node/Vite `/api/*` provider middleware require a reachable remote backend/proxy. Those server-side credentials must not be embedded in the IPA.
