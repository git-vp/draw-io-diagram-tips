# draw-io-diagram-tips
This repository gives tips to draw different type of diagrams in draw.io.
For example, to draw an interactive diagram such as the below:

![SSDLC Workflow](https://github.com/git-vp/draw-io-diagram-tips/assets/25417872/5ac60c6a-8ad4-44c0-a015-3ef77b968132)


## How to Draw Interactive Lines
* Open draw.io in a browser
* Open `Create New Diagram`
* Choose `Flowchart` template
* Choose `Edit -> Select Edges`
* Open `View -> Format` pane
* In `Style -> Properties` select `Flow animation` checkbox

## How to Toggle between Layers
* To demonstrate this I am going to draw an example SSDLC (Secure Software Development Lifecycle) workflow.
* This workflow contains two layers
  * Layer 1 - SSDLC workflow
  * Layer 2 - Associated commentary
* Perform the following in `Layer 1 - SSDLC workflow`
  * Right click on `Background` layer in `Layers` windows. Click on Pen icon and assign the following:
    * label: SSDLC Workflow
    * ID: change the default (system assigned) ID to something like L1. To do that, double click on the value and it should open a dialog where you can change the value
  * Draw up your SSDLC workflow
  * Add a text box called `See SSDLC Commentary` and colour it `Grey`. `Note:` This text box is used as a clickable item to switch between layers
* To add commentary to Layer 1, click on Lock button on the `SSDLC workflow` layer in the Layers window. This will ensure no further changes can be added to the Layer 1
* To add commentary to Layer 2,
  * Click on `+` sign on the `Layers` window. This will add another layer
  * Right click on added layer in `Layers` windows. Click on Pen icon and assign the following:
    * label: SSDLC Commentary
    * ID: change the default (system assigned) ID to something like L2. To do that, double click on the value and it should open a dialog where you can change the value
  * Now add additional commentary in the form of boxes with text to this layer now
  * Similar to Layer 1, add a text box called `Hide SSDLC Commentary` and colour it `Orange`
* Now to use the clickable text box to switch between layers, select Grey coloured `See SSDLC Commentary` text box, and click on `Edit -> Edit Link` from the menu
  * In the `Edit Link` dialog box, add the following text, where L2 is the ID of Layer 2 in the Layers window
    `data:action/json,{"actions":[{"toggle": {"cells": ["L2"]}}]}`
* Now select Orange coloured `Hide SSDLC Commentary` text box, and click on `Edit -> Edit Link` from the menu
  * In the `Edit Link` dialog box, add the following text, where L2 is the ID of Layer 2 in the Layers window
    `data:action/json,{"actions":[{"hide": {"cells": ["L2"]}}]}`

## How to Add Formatted Tool Tip Data
* Select an object for which you want to add tool tip
* Choose `Edit -> Edit Tooltip` option from the menu
* Add tool tip text data. Note, tool tip uses HTML formatting. Therefore, you want to add bullets, sub-bullets or bold text follow HTML format. For example:
  ```html
    <ul>
      <li>Requirements and acceptance criteria</li>
      <li>Test coverage / Level of testing</li>
      <li><b>Target architecture requirements</b></li>
      <li><b>Application Security requirements</b></li>    
      <li>Feature toggle requirements</li>
      <li><b>Licensing and Compliance needs</b></li>
      <li>Budget and Cost impact</li>
    </ul>
  ```

## References
* [Drawing Diagram in Draw.io with Custom Links and Actions](https://drawio-app.com/blog/interactive-diagrams-with-custom-links-and-actions/)
* [Draw.io Custom Tool to Generate Custom Link](https://jgraph.github.io/drawio-tools/tools/link.html)
  
