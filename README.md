# RedBrick AI Quickstart

This guide provides a step-by-step overview for setting up and managing projects in RedBrick AI, from creating taxonomies to organizing workflows and annotating data.

## Project Setup

### Key Steps
1. **Create a Taxonomy**: Define the labels and attributes to be used in your project.
2. **Set Up a Project**: Configure workflows tailored to your data and team.
3. **Add Data**: Upload or link your datasets via cloud storage.
4. **Organize Team Roles**: Assign tasks for labeling and review stages.

**Watch Project Setup Video:** [RedBrick Project Setup](https://www.youtube.com/watch?v=J0Wf1Kvhfv0&list=PLjI4V6WYNAySdSCPx0oI1pMo9hhrr7OA5)

---

### Building a Taxonomy

A taxonomy is the backbone of your labeling project. It defines the labels and attributes required for annotation.

1. **Create Labels:** Examples include “Liver,” “Kidneys,” and “Spleen” for organ segmentation.
2. **Define Label Types:** Options include segmentation, landmarks, length/angle measurements, and bounding boxes.
3. **Add Attributes:** Attributes can be boolean, dropdowns (single/multi-select), or text. For instance, you can add a “Variant Anatomy” attribute to organ labels.
4. **Assign Attributes to Levels:** Attributes can apply to an instance, series, or study—e.g., study-level quality attributes.

**Steps to Create a Taxonomy:**
- Navigate to the **Taxonomies** tab.
- Select **New Taxonomy** and define labels, attributes, and hints. For example, create a “Lung Tumor” label with a boolean attribute for “Cavitation Present” and include helpful instructions under **Hint**.

---

### Creating a Project

Once your taxonomy is ready, you can create a project to structure your workflow.

1. **Create a New Project:**
   - Click the **+** button under the **Home** section in the left toolbar.
   - Choose to create a **Project**, **Workspace**, or **Section** (folder).
   - Projects are tied to single datasets and taxonomies, while workspaces allow multiple projects using the same dataset.

2. **Configure Workflow:**
   - Define project settings, assign the taxonomy, and configure variables such as single vs. multiple labeling.

**Single vs. Multiple Labeling:**
- **Single Labeling:** Ideal for most use cases; efficient and practical.
- **Consensus Labeling:** Suitable for complex tasks; allows expert annotators to compare and select the best label using similarity scores.
- **Multi-Output Labeling:** Best for ambiguous tasks; stores multiple subjective labels for model training.

---

### Pipeline Stages

Customize your workflow with various pipeline stages:

1. **Multiple Labeling:** Choose to use single labeling or a multiple labeling strategy.
1. **Pre-Review Stage:** Perform an initial quality check before labeling begins.
2. **Auto-Annotator:** Use a pretrained or custom model to automate segmentation of normal anatomy.
3. **Pre-Label Stage:** Add metadata or classify studies for better annotator guidance.
4. **Review Stages:** Set up one or more review stages for quality control, either as fractional spot checks or comprehensive reviews.

---

### Adding Data

RedBrick supports multiple imaging formats like DICOM and NIFTI. Data can be uploaded directly or added via cloud integration.

**Uploading Data:**
- Drag and drop files into the **Data** tab within your project.

**Adding Cloud Data:**
- Navigate to **Integrations** > **New Storage Method** and configure a new cloud storage method.
- In the project’s **Data** tab, select **Upload Data** > **External Data** and choose the configured cloud source.

Note: When adding DICOM or NIFTI data, you can choose to group by study or treat each series as a separate task.

---

### Organizing the Workforce

Define team roles and assign tasks to streamline the labeling and review process.

---

## Workflow Templates

### Lone Wolf Labeling
- **Use Case:** Small teams or individual annotators.
- **Workflow:** Single labeling with one review stage for quality checks.
- **Setup:** Add one review stage during project creation.

### The Wolf Pack
- **Use Case:** Teams with varying experience levels.
- **Workflow:**
  - Less experienced annotators draft labels.
  - Experienced annotators refine labels in a second stage.
  - Final review by team leads or experts.
- **Setup:** Add two review stages.

### Difficult Cases
- **Use Case:** Expert annotators creating highest quality labels from complex datasets with well defined criteria for labels.
- **Workflow:**
  - Expert annotators create multiple labels for each study.
  - Similarity scores are calculated for each label.
  - The best or consensus label is chosen manually, taking into account similarity scores.
- **Setup:** Select multiple labeling when creating a project. Toggle to single output and manual merge. Select the number of labelers you would like to annotate each study. 

### Orientation
- **Use Case:** Training and skill assessment for new annotators.
- **Workflow:**
  - Create a set of ground truth annotations
  - 

---

## Workflow for Annotators

### Getting Started

1. Open your project from the **Projects** section.
2. Select **Queued for Labeling** to view assigned studies. Use **Recently Labeled** to revisit completed tasks.
3. Click **Label** to start annotating.

### Labeling Tools

1. **Viewer Configuration:** Organize views (e.g., axial, coronal, sagittal) and adjust image contrast using the **Windowing Tool**.
2. **Select a Label:** Use the **Taxonomy** toolbar or numeric shortcuts.
3. **Segmentation Tools:**
   - **F.A.S.T. Tool:** Automatically generates 2D segmentations.
   - **Mask Propagation Tool:** Creates 3D segmentations from 2D slices.
4. **Study/Series Classification:** Answer questions about study quality.
5. **Final Steps:** Submit completed labels or flag issues using **Raise Issue** in the **Skip** menu.
6. **Communication:** Check the **Comment** tab for reviewer feedback.

---

## Workflow for Reviewers

### Getting Started

1. Access the **Review Queue** to see studies requiring review.
2. Verify labels and provide feedback.
3. Use the **Comment** section for detailed notes.
4. Finalize labels as **Ground Truth** or return for revision.

---

## Additional Resources

- [RedBrick Documentation](https://docs.redbrickai.com/)
- [RedBrick YouTube Channel](https://www.youtube.com/channel/UCb9AKo2XaZsxI7D-foIQ4lA)
