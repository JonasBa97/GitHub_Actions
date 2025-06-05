# GitHub-Actions

## Grundlagen zu GitHub-Actions
- Sturktur für Pipline
- .github/workflows/main.yaml

## Beispiel für .yaml-Struktur
```yaml
name: xxx --> benennt die Actions
on: [push] --> Action wird durch push gestartet

jobs:
  build:
    runs-on: ubuntu-latest --> setzt Attribut für verwendets Betriebssystem
    steps: --> zu durchlaufende Schritte der Pipeline
      - name: "clone and checkout git repo"
        uses: actions/checkout@v4
        #run: | 
        #  git clone https://github.com/JonasBa97/GitHub_Actions.git
        #  git fetch --all
        #  git checkout master
      - name: "Node.js 18 installieren"
        uses: actions/setup-node@v4
        with:
          node-version: '18'
        #run: | 
        #  curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash
        #  sudo apt-get install -y nodejs
        #  node -v
        #  npm -v
```