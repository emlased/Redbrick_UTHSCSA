# RedBrick AI Quickstart

## Project Admin
[Here](https://www.youtube.com/watch?v=J0Wf1Kvhfv0&list=PLjI4V6WYNAySdSCPx0oI1pMo9hhrr7OA5) is a short youtube playlist showing the process of setting up a project in RedBrick.

### Linking Data
When adding data, it needs to be housed externally if privacy is a concern. Uploaded data will be stored on RedBrick servers. Complete the following steps to set up external storage. [Here](https://docs.redbrickai.com/importing-data/import-cloud-data) is documentation regarding cloud storage. 
1. 

### Project Setup
1. Select the Taxonomies section on the left main toolbar. This will allow you to define label names and types as well as organize labels into directories. Different labels include segmentations, distance measurements, angle measurements, bounding boxes, and more. [Here](https://docs.redbrickai.com/projects/taxonomies) is a detailed description of available taxonomies. For lung nodule segmentation, the label type is a segmentation and the label name could be Lung_nodule.
1. In the Home page, select New Project in the top right corner. Select an appropriate taxonomy.
1. When designing a pipeline, you can add multiple review stages and define what fraction of labels must pass through each stage. For lung nodule segmentation, a simple pipeline where 100% of labels are reviewed a single time is recommended.
1. 
 
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
1. After selecting a label, the segmentation toolbar will appear on top of the screen. Some segmentation tools that may be useful for lung nodules include... If the Boost tool is enabled, then the F.A.S.T. tool is unlocked. This tool integrates the SAM tool to automatically generate a 2D segmentation. These can be generated either by a bounding box or by holding alt and hovering over the object of interest. The Mask Propagation tool is similar to F.A.S.T.; however, it generates a 3D segmentation starting from a segmentated slice and moving outwards over a specified range. While this is the most powerful semiautomated tool in RedBrick, the other tools are often enough to quickly generate segmentations depending on the study.
1. After completing the segmentation, expend the Study Classification and Series Classification dropdowns. These may include questions regarding study quality.
1. If the label is complete and ready for submission, you can press the blue submit button. If there is an issue segmenting the study, select the skip button and select raise issue. This will remove the study from the pipeline so that the issue can be evaluated by project admin. 
1. Review the comment tab located in the top toolbar. This sections serves as a line of communication between labelers and reviewers.
1. As your labels pass through the review process, some may be accepted and tagged as Ground Truth while others may be recycled in you Queue for adjustments. The Project Overview page allows you to check the status of your labels. 

## For Reviewers
