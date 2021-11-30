# Mermaid JS Arrowhead Substitution

This is documentation for a simple command which allows for modifying the fill of the arrowheads generated by [mermaidjs](https://mermaid-js.github.io/mermaid/#/classDiagram) class diagrams.
This allows for quick generation of UML class diagrams programmatically using mermaid whilst allowing to adhere to different diagram styles.

### Original
![original](https://github.com/owdevel/mermaidjs-class-arrowheads/blob/master/test.svg?raw=true)

### Modified
![original](https://github.com/owdevel/mermaidjs-class-arrowheads/blob/master/output.svg?raw=true)

## General Workflow

1. Generate a `.svg` from mermaid.js, there are a couple easy ways to do this
   - [Mermaid Live Editor](https://mermaid.live) - Browser Based Editor Download as SVG
   - [VSCode Mermaid Editor](https://marketplace.visualstudio.com/items?itemName=tomoyukim.vscode-mermaid-editor) - Extension for VSCode that allows for live editing and saving as svg
2. Run one of the two `sed` commands below, replacing `file.svg` with your input file

## SED Commands

### Modify In Place File

```sh
sed -i -r 's/\.(extension|aggregation)\{fill:#([0-9A-Fa-f]+)/\.\1\{fill:#ECECFF/g' file.svg
```

### Export to External File

```sh
sed -r 's/\.(extension|aggregation)\{fill:#([0-9A-Fa-f]+)/\.\1\{fill:#ECECFF/g' file.svg > output.svg
```

### Customising Color
The color can be customised by replacing `#ECECFF` in the regex with any hex color code.
