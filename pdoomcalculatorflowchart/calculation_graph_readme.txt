# Calculation Graph Documentation

This document explains the functionality and implementation of the `calculation_graph.html` page.

## HOW THE PAGE WORKS

*   **Visualization:** The page displays a directed graph representing the dependencies between different calculated probabilities related to AI risk scenarios.
*   **Layout:**
    *   Nodes flow from left to right, starting with input probabilities (green circles) on the far left, progressing through intermediate derived probabilities (purple circles), and ending with the final output probabilities (red circles) on the far right.
    *   Nodes are arranged in layers based on their calculation dependency. All nodes within a layer share a similar vertical position (x-coordinate), ensuring that connecting edges generally move from left to right.
*   **Interaction:**
    *   **Hovering:** When you hover your mouse cursor over a node (circle), a tooltip appears displaying:
        *   `ID`: The unique identifier for the probability variable.
        *   `Type`: Whether it's an 'input', 'derived', or 'output' node.
        *   `Layer`: The calculated dependency layer (0 for inputs, increasing towards outputs).
        *   `Probability`: The (currently placeholder) probability value associated with the node.
        *   `Calculation`: A description of how this probability is derived (or that it's a base input).
    *   **Dragging:** You can click and drag any node to temporarily reposition it, which can help untangle complex areas of the graph. The simulation will continue to apply forces, so the node might drift back towards its original layer.
*   **Navigation:** A link in the top-right corner ("Back to Sankey Diagram") allows navigation back to the main `page.html`.

## HOW THE CODE WORKS

*   **HTML (`calculation_graph.html`):**
    *   Sets up the basic page structure, including the title, linking the CSS (`calculation_graph.css`), and including the D3.js library.
    *   Contains an SVG element (`<svg id="calculation-graph">`) where the graph is rendered.
    *   Holds the JavaScript code within `<script>` tags.
*   **CSS (`calculation_graph.css`):**
    *   Styles the overall page layout (body, container).
    *   Defines the appearance of the graph elements:
        *   `link`: Styles for the edges (lines) connecting nodes (stroke color, opacity, width).
        *   `node circle`: Base styles for the node circles (size, stroke).
        *   `.node.input`, `.node.derived`, `.node.output`: Specific styles (fill color, size) for each node type.
        *   `.node text`: Styles for the text labels above each node (font size, color, positioning).
        *   `:hover` pseudo-classes: Define visual changes when hovering over nodes (e.g., darker stroke, larger radius, bold text).
    *   Styles the arrowhead marker (`svg defs marker`).
*   **JavaScript (within `calculation_graph.html`):**
    *   **Data (`graphData`):** Defines the graph structure:
        *   `nodes`: An array of objects, each representing a node. Key properties include `id`, `type`, `layer` (for layout), `probability` (for tooltip), and `description` (for tooltip).
        *   `links`: An array of objects defining the edges, specifying `source` and `target` node IDs.
    *   **D3 Setup:**
        *   Selects the SVG container and sets its viewBox and aspect ratio.
        *   Defines an arrowhead marker (`<marker>`) within SVG `<defs>` for use on the links.
    *   **Force Simulation (`d3.forceSimulation`):**
        *   Initializes the simulation with the `graphData.nodes`.
        *   `forceLink`: Creates forces that pull linked nodes together, based on `graphData.links`. `distance()` sets the ideal link length.
        *   `forceManyBody`: Creates repulsion forces between all nodes to prevent overlap. `strength()` controls the repulsion intensity.
        *   `forceCenter`: Gently pulls all nodes towards the center of the SVG.
        *   `forceX`: **Crucially implements the layering.** It pulls each node towards a specific x-coordinate calculated based on its `layer` property and the total `numLayers`. A high `strength()` ensures nodes strongly adhere to their layer.
        *   `forceY`: Gently pulls nodes towards the vertical center.
    *   **Rendering:**
        *   Creates SVG `line` elements for each link in `graphData.links`.
        *   Creates SVG `g` (group) elements for each node in `graphData.nodes`. Each group contains a `circle` and a `text` label.
        *   Appends a `title` element to each node group, which acts as the browser's native tooltip. The content is dynamically generated based on the node's data (`id`, `type`, `layer`, `probability`, `description`).
    *   **Tick Function (`simulation.on("tick", ...)`):** This function runs repeatedly as the simulation converges. On each "tick":
        *   It updates the `x1`, `y1`, `x2`, `y2` attributes of the links based on the current positions of their source and target nodes.
        *   It updates the `transform` attribute of the node groups to reflect the node's new `x` and `y` coordinates.
        *   It includes logic to constrain nodes within the SVG boundaries (though the `forceX` largely handles horizontal positioning).
    *   **Drag Functionality:** Implements standard D3 drag behavior, allowing users to temporarily override the simulation forces by fixing a node's position (`fx`, `fy`) while dragging. Releasing the node sets `fx` and `fy` back to `null`, allowing the simulation to take over again.

The nodes should go left to right. Meaning input nodes are on the left, and move to the right.

Also, the nodes should be layered (have same x-coordinate) so that no edges go right to left.

Also, make it somewhat bigger.

Also, when you hover over the nodes, you should see a probability and a description of how its calculated