========================================================================
P(Doom) Sankey Diagram Visualization Script
========================================================================

Purpose:
--------
This script calculates the probability of various future scenarios
related to Artificial General Intelligence (AGI) development over the
next 10 years, focusing on the potential for existential risk ("doom").
It takes several key probability estimates as inputs and uses them to
compute the flow of possibilities through different stages. The results
are then visualized as an interactive Sankey diagram using the D3.js
library and the d3-sankey plugin.

Dependencies:
-------------
- D3.js (v7): Core data visualization library.
- d3-sankey (v0.12.3): D3 plugin for creating Sankey diagrams.
  (Included via CDN in the <head> section of the HTML)

Probability Model Stages:
-------------------------
The calculation follows a branching path based on conditional probabilities:
1. Initial State: Represents the total probability space (100%).
2. Pause/Slowdown: Splits based on the chance of a significant pause
   in AI development.
3. AGI Development (Given No Pause): If there's no pause, what's the
   chance AGI is developed within 10 years?
4. RLHF Sufficiency (Given AGI): If AGI is developed, is Reinforcement
   Learning from Human Feedback (RLHF) sufficient for alignment?
5. Alignment Breakthrough (Given RLHF Insufficient): If RLHF isn't
   enough, is there a breakthrough in alignment techniques?
6. Final Outcome (Given Alignment Method): Based on whether alignment
   was achieved via RLHF or a breakthrough (or not at all), what is
   the final outcome (Survival vs. Bad Outcome - Doom/Dystopia)?
   -> NEW: If no breakthrough, considers if control methods suffice.
   -> NEWER: If control initially suffices, considers if it holds.

Code Structure:
---------------
1. INPUT VARIABLES: Defines the core probabilities used in the model.
   -> Modify these constants to explore different scenarios:
      - p_pause
      - p_agi_given_no_pause
      - p_rlhf_suffices_given_agi
      - p_breakthrough_given_rlhf_insufficient
      - p_dystopia_given_alignment (also used for P(Bad | Control OK))
      - p_control_monitor_automated_alignment_works_conditional_no_breakthrough
2. CALCULATIONS: Computes the probabilities for each node and link
   in the Sankey diagram based on the input variables.
3. D3 SANKEY SETUP: Configures and renders the Sankey diagram.
   - Define Data Structure: Creates the `nodes` and `links` arrays
     required by d3-sankey, mapping calculated probabilities to link values.
   - Setup SVG Dimensions: Configures the size and margins for the SVG
     container (`#sankey-chart`).
   - Create SVG Element: Appends the main SVG and group elements to the DOM.
   - Setup Sankey Layout Generator: Initializes `d3.sankey()` with
     specific configurations (node width, padding, alignment, sorting).
     Includes custom sorting logic to attempt a more intuitive layout.
   - Compute Layout: Calculates the positions (x, y coordinates) and
     sizes for nodes and links. Includes manual adjustments for specific
     node/link positions for better visual clarity.
   - Define Color Scale: Sets up a function to color nodes based on their name/type.
   - Draw Links: Renders the paths representing the probability flows.
   - Draw Nodes: Renders the rectangles representing the stages/outcomes.
   - Add Node Labels: Adds text labels next to the nodes, showing names
     and calculated percentages.
4. Update Final Result Display: Populates the `<h2>` tag within the
   `#result` div with the final calculated P(Bad Outcome).
5. Verification (Console Logs): Outputs key calculated probabilities
   to the browser's developer console for debugging and verification.

HTML Interaction:
-----------------
- Reads input variables defined directly in the script.
- Renders the Sankey diagram into the `<svg id="sankey-chart">` element.
- Displays the final calculated P(Bad Outcome) in the
  `<span id="final-p-doom">` element within the `<div id="result">`.

========================================================================
STRUCTURE OF SNAKEY DIAGRAM (IN THE ORDER THEY HAVE TOP TO BOTTOM IN DIAGRAM)
Layer1 : [Initial Worlds]
Layer2 : [No Pause, Pause Occurs]
Layer3 : [AGI develops, No AGI (No Pause), Survive (Pause)]
Layer4 : [RLHF Insufficient, RLHF Sufficient, Survive (No AGI)]
Layer5 : [No Breakthrough, Alignment Breakthrough, Survive (RLHF)", Dystopia]
Layer6 : [Control Fails, Control Succeeds, Survival (Breakthrough), Dystopia]
Layer7 : [Dystopia(Control), Survival(Control)]
Layer8 : [Doom]
========================================================================
