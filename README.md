# Introduction
This guide outlines the key steps for setting up a new project on the RedBrick platform and includes a quick walkthrough to help teams get started.

---

## Creating a Project
When creating a new project on RedBrick, a team must designate a lead who will be given admin access to create and set up a project. Here is an overview of the steps involved in a labeling project:

1. **Data Import**: Prepare data for labeling.
2. **Labeling Taxonomy**: Create a clear schema of labels and attributes to help improve the quality of labeled data.
3. **Team Roles and Responsibilities**: Define roles and permissions of the labeling team.
4. **Project Workflow**: Define process for labeling and quality assurance.
5. **Segmentation Guide**: Overview of labeling tools.
6. **Data Export**: How to access data.

---

## Labeling Taxonomy
Taxonomies help organize how you label data in RedBrick AI, ensuring consistency across projects. When setting up a taxonomy, you'll define:
- **Types of Labels**: Examples include Segmentation or Bounding Boxes.
- **Label Names**: Such as "Edema."
- **Attributes**: Add extra details using checkboxes (True/False), dropdown options, multiple choices, or text fields.
- **Classifications**: Attributes added to studies, series, or video frames to provide more information.
- **Hints**: Instructions visible when hovering over labels.

To create a taxonomy:
1. Navigate to the **Taxonomies** tab.
2. Select **New Taxonomy**.
3. Define labels, attributes, and hints.

---

## Team Roles and Responsibilities
The core team includes:
- **Internal Reviewers**: Serve as Project Admins, manage labeling stages, and conduct quality reviews.
- **Labelers**: Perform data annotation as directed by Internal Reviewers.

Additional roles may include:
- **External Reviewers**: Validate labels during the review stage.
- **External Project Managers**: Oversee tasks with full admin privileges.

### Example Roles
- **Labelers**: Medical students and residents.
- **Internal Reviewers**: Residents.
- **External Reviewers/Managers**: Faculty or industry clients.

To add team members:
1. Navigate to the **Team** tab.
2. Select **Invite member**.
3. Assign appropriate roles (Project Member, Admin, etc.).

---

## Project Workflow
RedBrick workflows can be customized based on team needs. Key features include:

### Pre-Review
- An optional stage for evaluating data before labeling.

### Single Labeling
- Studies are labeled once by each annotator.

### Multiple Labeling
- Studies receive several labels, and **Similarity Scores** identify discrepancies for review.

### Review Stage
- Labels are validated post-labeling. Internal and external reviews are recommended for quality assurance.

---

## Completing a Project
### Assigning Tasks
Tasks are usually auto-assigned but can be managed manually in the **Data** tab.

---

## Labeling Quickstart
### Recommended Workflows
1. **Rapid Labeling**: For small teams or quick prototypes.
2. **Test Batch**: To refine instructions and establish a gold standard.
3. **Tiered Labeling**: For time-intensive projects like segmentation.
4. **Consensus Labeling**: For less intensive tasks like bounding boxes.

#### Rapid Labeling
1. Add team members.
2. Define labeling taxonomy.
3. Create a project.
4. Use single labeling with optional review stages.

#### Test Batch
1. Add team members.
2. Define labeling taxonomy.
3. Create a project with multiple labeling.
4. Assign 2 labelers per study and review similarity scores.

#### Tiered Labeling
1. Use a pre-defined taxonomy.
2. Include internal and external review stages.
3. Finalize and export labels after reviews.

#### Consensus Labeling
1. Use multiple labeling with single output and manual selection.
2. Conduct manual reviews to ensure quality.

---

## Other Cases
### Clinical Validation Testing
Use a similar workflow to gold standard labeling but blind labelers to model-generated labels. Compare **Similarity Scores** between the model and human labels.
