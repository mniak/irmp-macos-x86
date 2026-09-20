# IRMP macOS x86_64 wrapper

This repository contains the IRMP shared-library wrapper used by libsigrokdecode for decoding infrared protocols.

It is a small packaging of the upstream IRMP sources together with the public C API used by the Python bridge.

## Build

```bash
clang -arch x86_64 -shared -fPIC \
  -I. \
  -Dunix \
  -o libirmp.dylib \
  irmp-main-sharedlib.c \
  -lglib-2.0 -framework Python
```

If you prefer a more reproducible setup, use the GitHub Actions workflow in `.github/workflows/build-macos-x86_64.yml`.
