# build-apple-platforms Action

A GitHub Action to build a project for all  platforms: iOS, macOS, tvOS, watchOS and visionOS.

Useful to catch compatibility issues when working on a project or framework that supports mutliple platforms.

NOT useful for deployment since it only builds for simulators and doesn't support signing.

Requires `macos-15` to build for visionOS

Example:

```yaml
name: Build Project

on:
  push:

jobs:
  build:
    runs-on: macos-15
    
    steps:
    - name: Checkout code
      uses: actions/checkout@v3

    - name: Build Apple Platforms Action
      uses: EmilioPelaez/build-apple-platforms@v1.0.0
      with:
        project: 'Example/HierarchyResponderExample.xcodeproj'
        scheme: 'HierarchyResponderExample'
        watch_scheme: 'HierarchyResponderExampleWatch'
```
