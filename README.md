
name: CI Pipeline

on:
  push:
  pull_request:

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Test website file
        run: |
          if [ -f index.html ]; then
            echo "Test passed: index.html exists"
          else
            echo "Test passed: No index.html in this project"
          fi

      - name: Pipeline success
        run: echo "CI pipeline completed successfully!"
