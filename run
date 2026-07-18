#!/usr/bin/env bash
set -euo pipefail
cd "$(dirname "${BASH_SOURCE[0]}")"

cmd="${1:-}"

case "$cmd" in
  pull)
    git pull
    ;;
  push)
    git add -A
    git commit -m "Update thesis" || echo "Nothing to commit"
    git push
    ;;
  build)
    latexmk -pdf -interaction=nonstopmode Thesis.tex
    ;;
  clean)
    latexmk -C
    ;;
  *)
    echo "Usage: ./run {pull|push|build|clean}"
    exit 1
    ;;
esac
