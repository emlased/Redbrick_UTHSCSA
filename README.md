# RedBrick AI Quickstart

## For Labelers
[Here](https://www.youtube.com/watch?v=cl7oTHeIhsc&list=PLjI4V6WYNAyS9PGIYVabokPNri_wLeYAQ) is a short youtube playlist showing the annotation process for labelers.

### Setup
1. Open the project from the toolbar on the left.
1. From the dropdown select Queued for Labeling to see a list of studies assigned for labeling. The Recently Labeled option allows you to view the status of studies you have already labeled.  
1. Select the label button in the top right to begin labeling.
1. In the Viewer, organize the display panels. For lung nodules, it is helpful to have axial, coronal, and saggital views. Use the windowing tool (Sun icon) to select an appropriate window.

### Labeling
RedBrick includes a number of advanced tools for labeling. [Here](https://www.youtube.com/watch?v=wsDFtPv64IM&list=PLjI4V6WYNAyTuh9PWDKF_N8k2lEdD47qz) is a youtube playlist reviewing the segmentation toolkit. Detailed documentation of the toolkit can be found [here](https://docs.redbrickai.com/annotation-and-viewer/segmentation/segmentation-tools).
1. To begin a label, select the kind of label from the taxonomy toolbar on the left. You can either select the label using the plus sign next to the label name or use the numeric shortcut associated with the label name. Note that if you are labeling a number of the similar items (like multiple vertebrae), you can either use semantic labeling where each item falls under the same label or instance labeling where each item is given its own label. For lung nodule segmentation, semantic labeling is recommended where multiple nodules (if present) are included in a single label.
1. After selecting a label, the segmentation toolbar will appear on top of the screen. Some segmentation tools that may be useful for lung nodules include
1. After completing the segmentation, expend the Study Classification and Series Classification dropdowns. These may include questions regarding study quality.
1. Review the comment tab located in the top toolbar. This sections serves as a line of communication between labelers and reviewers.
1. As your labels pass through the review process, some may be accepted and tagged as Ground Truth while others may be recycled in you Queue for adjustments. The Project OVerview page allows you to check the status of your labels. 
