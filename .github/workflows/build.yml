name: build
on:
  push:
  workflow_dispatch:
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-java@v4
        with:
          distribution: temurin
          java-version: 21
      - uses: gradle/actions/setup-gradle@v4
        with:
          gradle-version: 8.10.2
      - run: |
          unzip -q pzy-arms-src.zip -d proj
          cd proj
          gradle build --no-daemon
      - uses: actions/upload-artifact@v4
        with:
          name: pzy-arms
          path: proj/build/libs/pzy-arms-0.1.0.jar
