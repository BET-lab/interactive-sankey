# Interactive Sankey Diagram

An interactive Sankey diagram visualization built with D3.js that supports progressive disclosure and customizable styling.

## Features

- **Progressive Disclosure**: Start with root nodes and click to reveal connected nodes and flows
- **Interactive Exploration**: Click on nodes to expand the diagram progressively
- **Customizable Styling**: Adjust node colors, sizes, link opacity, and other visual properties
- **Gradient Links**: Beautiful gradient colors for flow connections
- **SVG Icons**: Custom SVG icons for each node type
- **Responsive Design**: Works on desktop and mobile devices
- **Tooltips**: Hover over nodes and links for detailed information
- **Smooth Animations**: Elegant transitions when revealing new elements

## Quick Start

1. Clone or download the project files
2. Place the files in a web server directory (local or remote)
3. Open `index.html` in a web browser
4. The diagram will load automatically with sample energy flow data

## Files Structure

```
interactive-sankey/
├── index.html          # Main application file
├── data.json          # Data file containing nodes and links
└── README.md          # This file
```

## Data Format

The visualization uses a JSON format that defines nodes, links, and interaction rules:

```json
{
  "nodes": [
    {
      "id": "unique_id",
      "name": "Display Name",
      "level": 0,
      "style": {
        "color": "#color_code",
        "icon": "<svg>...</svg>"
      },
      "visible": true,
      "description": "Node description"
    }
  ],
  "links": [
    {
      "id": "link_id",
      "source": "source_node_id",
      "target": "target_node_id",
      "value": 100,
      "style": {
        "gradient": {
          "start": "#start_color",
          "end": "#end_color"
        }
      }
    }
  ],
  "interactionRules": {
    "initiallyVisible": ["node_id"],
    "progressiveDisclosure": {
      "parent_node": ["child_node1", "child_node2"]
    }
  }
}
```

## Customization

### Visual Controls

The interface includes several customization controls:

- **Node Width**: Adjust the thickness of nodes
- **Node Padding**: Control spacing between nodes
- **Node Color**: Change the default node color
- **Link Opacity**: Adjust transparency of flow connections
- **Animation Speed**: Control transition timing

### Data Customization

1. **Modify `data.json`**: Edit the data file to include your own nodes and links
2. **Node Styling**: Each node can have custom colors and SVG icons
3. **Link Gradients**: Define custom gradient colors for each connection
4. **Interaction Rules**: Set which nodes are initially visible and define progressive disclosure paths

### Adding Custom Icons

Replace the `icon` field in node definitions with your own SVG code:

```json
{
  "style": {
    "icon": "<svg viewBox='0 0 24 24' width='20' height='20'><path d='...' fill='white'/></svg>"
  }
}
```

## How It Works

1. **Initial State**: Only the root nodes specified in `interactionRules.initiallyVisible` are shown
2. **Progressive Disclosure**: Click on any visible node to reveal its connected nodes
3. **Flow Visualization**: Links between nodes show the flow relationships with gradient colors
4. **Interactive Exploration**: Continue clicking to explore deeper levels of the data

## Browser Support

- Chrome (recommended)
- Firefox
- Safari
- Edge
- Modern mobile browsers

## Dependencies

- D3.js v7 (loaded from CDN)
- d3-sankey plugin (loaded from CDN)

## Sample Data

The included sample data demonstrates an energy flow visualization with:
- Energy sources (coal, natural gas, renewables)
- Renewable breakdowns (solar, wind, hydro)
- Electricity grid distribution
- End-use consumption (residential, commercial, industrial)

## License

MIT License - feel free to use and modify for your projects.

## Contributing

Feel free to submit issues and enhancement requests!