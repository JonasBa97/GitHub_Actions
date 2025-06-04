# GitHub-Actions

## Grundlagen zu GitHub-Actions
- Sturktur für Pipline
- .github/workflows/main.yaml

## Beispiel für .yaml-Struktur
name: xxx --> benennt die Actions
on: [push] --> Action wird durch push gestartet

jobs:
  build:
    runs-on: ubuntu-latest --> setzt Attribut für verwendets Betriebssystem
    steps: --> zu durchlaufende Schritte der Pipeline
      - name: "Clone git repo"
        run: | 
          git clone https://github.com/JonasBa97/GitHub_Actions.git
        #  git fetch --all
        #  git checkout master
      - name: "Node.js 18 installieren"
        run: | 
          curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash
          sudo apt-get install -y nodejs
          node -v
          npm -v