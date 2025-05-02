========================================================================
P(Doom) Sankey Diagram Visualization
========================================================================

Overview
--------
This project visualizes the probability flow of existential risk ("doom") from advanced AI over the next 10 years, using a Sankey diagram. The model is based on a series of conditional probabilities representing key events and alignment challenges in AI development.

The visualization is interactive and built with D3.js and d3-sankey, and is fully client-side (HTML+JS+CSS).

Key Features
------------
- **Sankey Diagram**: Clearly shows how probability mass flows from initial uncertainty through various AI development and alignment scenarios to final outcomes (survival or doom).
- **Customizable Probabilities**: All key probabilities are defined at the top of the script for easy adjustment and scenario analysis.
- **Responsive Design**: The diagram and page layout adapt to different screen sizes.
- **Clear Outcome Display**: The final calculated probability of doom is prominently displayed, with contextual color and emoji.

How the Model Works
-------------------
The model is a sequence of conditional events, each with a user-defined probability:

1. **Pause**: Probability that a significant pause in AI development prevents ASI (Artificial Superintelligence) in the next 10 years.
2. **ASI Development**: If no pause, probability that ASI is developed within 10 years.
3. **RLHF Sufficiency**: If ASI is developed, probability that RLHF (Reinforcement Learning from Human Feedback) or similar methods are sufficient to align ASI.
4. **Alignment Breakthrough**: If RLHF is insufficient, probability of a major breakthrough in alignment research.
5. **Control/Monitoring**: If no breakthrough, probability that control/monitoring/automated alignment methods work well enough to prevent doom.
6. **Bad Outcomes Despite Alignment**: For each alignment path, probability that things go badly even if alignment appears to succeed.

Each branch in the Sankey diagram represents one of these events, and the width of each flow is proportional to the probability of that path.

How to Use
----------
1. **Open `page.html` in your browser.**
2. **Adjust probabilities** at the top of the `<script>` section in `page.html` to explore different scenarios.
3. **View the Sankey diagram** and the final calculated P(Doom) on the page.

File Structure
--------------
- `page.html`   : Main HTML file, includes all logic and visualization.
- `page.css`    : Styles for the page and diagram.
- `readme.txt`  : This documentation.

Customization
-------------
- To change the probabilities, edit the constants at the top of the `<script>` in `page.html`.
- To change colors or layout, edit `page.css` and the color map in the JS.

Dependencies
------------
- [D3.js v7](https://d3js.org/)
- [d3-sankey v0.12.3](https://github.com/d3/d3-sankey)

Both are included via CDN in the HTML.

Limitations & Notes
-------------------
- The model assumes binary outcomes at each stage, which is a simplification.
- The probabilities are illustrative and should be set according to your own beliefs or scenario analysis.
- The diagram is not intended as a precise forecast, but as a tool for visualizing and reasoning about risk flows.

Credits
-------
- Diagram and model by [Your Name or Handle]
- Built with D3.js and d3-sankey

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
