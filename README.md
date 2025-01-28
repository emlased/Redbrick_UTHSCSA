# Introduction

This guide outlines the steps involved in setting up a new labeling project on the RedBrick platform.

---

## Table of Contents
1. [Team Roles and Responsibilities](#team-roles-and-responsibilities)
2. [Labeling Taxonomy](#labeling-taxonomy)
3. [Creating a Project](#creating-a-project)
4. [Importing Data](#importing-data)
5. [Segmentation Workflow](#segmentation-workflow)
6. [Exporting Data](#exporting-data)

---

## Team Roles and Responsibilities

The core team includes:
- **Team Lead**: Serves as Internal Reviewer, but this member has Organizational Admin status to set up new projects.
- **Internal Reviewers**: Serve as Project Admins, manage labeling stages, and conduct quality reviews.
- **Labelers**: Perform data annotation as directed by Internal Reviewers.

Additional roles may include:
- **External Reviewers**: Validate labels during the review stage.
- **External Project Managers**: Oversee tasks with full admin privileges.

### Example Roles
- **Labelers**: Medical students and residents.
- **Internal Reviewers**: Residents.
- **External Reviewers/Managers**: Faculty or industry clients.

> **To add team members:**
> 1. Navigate to the **Team** tab.
> 2. Select **Invite Member**.
> 3. Assign appropriate roles:
>    - **Project Members**: Labelers and External Reviewers.
>    - **Project Admins**: Internal Reviewers and External Managers.

---

## Labeling Taxonomy

Taxonomies define the labeling schema in RedBrick AI, ensuring consistency across projects. When setting up a taxonomy, you'll define:
- **Types of Labels**: Examples include Segmentation or Bounding Boxes.
- **Label Names**: Such as "Edema."
- **Attributes**: Add extra details using checkboxes (True/False), dropdown options, multiple choices, or text fields.
- **Classifications**: Attributes added to studies, series, or video frames to provide more information.
- **Hints**: Instructions visible when hovering over labels.

The following are examples of when you might add an attribute to a label.
- brain mass segmentation > suspected intra-axial vs extra-axial location
- liver segmentation > mass present vs absent
- lung nodule segmentation > clear vs indeterminate margins
- study classification > adequate vs poor quality

> **To create a taxonomy:**
> 1. Navigate to the **Taxonomies** tab.
> 2. Select **New Taxonomy**.
> 3. Define labels, attributes, and hints.

---

## Creating a Project

### Workflow Stages
- **Pre-Review**: Optional stage for evaluating data before labeling.
  - The reviewer can remove studies of poor quality from the labeling pool.
- **Single Labeling**: Studies are labeled once by each annotator.
- **Multiple Labeling**: Studies receive several labels, and **Similarity Scores** identify discrepancies for review.
  - **Single Output Labeling**: Manual or automated data merge stage to select the best labels.
  - **Multiple Output Labeling**: Includes all labels in the final dataset.
- **Review Stage**: Labels are validated post-labeling.
  - Any number of review stages can be added in series (complete or fractional).
  - Internal reviews are recommended prior to finalizing labels.

> **To create a project:**
> 1. Press the **+** symbol next to the **Home** tab.
> 2. Select **New Project**.
> 3. Name the project and select the appropriate taxonomy.
> 4. Add stages as needed. For basic projects, press **+ Add Review Stage**.

---

## Importing Data

There are several options for importing data into RedBrick. For projects importing data from the UTSA AI consortium or uploading prelabeled data, an **Items List** (.json file) must be generated and uploaded using the RedBRick CLI (command line interface).

### Adding a Storage Method

RedBrick supports multiple cloud storage integrations.

> **To add a storage method:**
> - Follow the steps in the RedBrick documentation.

### Creating an Items List

The **Items List** is a `.json` file that contains:
- A path to each item being imported.
- Metadata to organize items into tasks.

**Example Path**:  
`container/folder/item.dcm`

> **To create an Items List:**
> 1. In the **Integrations** tab, click **…** for your storage method and select **Verify Storage Method**.
> 2. Use a script to generate the `items.json` file for your data.

#### Importing Annotations
To include annotations, specify:
- A path to each segmentation file.
- A segment map associating segments with taxonomy items.

Segmentation files must be in **nifti** format.

[See Examples of Item Lists](https://docs.redbrickai.com/importing-data/import-cloud-data/creating-an-items-list)

### Adding Data to a Project

To import studies use the **RedBrick CLI**:
1. Install CLI.
2. Create a local project directory.
3. Upload the `items.json` file.

> **To Add Data Using the CLI**:
> 1. Create a virtual environment and install redbrick SDK/CLI.
> ```bash
> python -m venv venv &&
> source ./venv/bin/activate &&
> pip install -U redbrick-sdk
> ```
> 2. Generate API key under **Integrations** tab.
> 3. Copy OrgID from RedBrick Url. `https://app.redbrickai.com/<org_id>/projects/<project_id>`
> 4. Add CLI credentials.
> ```bash
> redbrick config
> ```
> 6. Copy StorageID from the Storage Method in the **Integrations** tab.
> 7. Upload items list. Use your own STORAGE ID.
> ```bash
> redbrick upload items.json --storage STORAGEID
> ```

---

## Segmentation Workflow

As studies move through the workflow:
- **Team Lead**: Monitors progress and assigns tasks.
- **Labelers and Reviewers**: Perform assigned labeling tasks.

### Task Assignment
- **Automated Assignment**: Default for labeling tasks.
- **Manual Assignment**: For review stages, assign studies to specific users.

### Segmentation Toolkit
- [Overview of the Labeling Process (Video)](https://www.youtube.com/watch?v=cl7oTHeIhsc)
- [Segmentation Toolkit Overview (Video)](https://www.youtube.com/watch?v=wsDFtPv64IM)

---

## Recommended Labeling Workflows

Workflows tailored to team sizes and project types:
- **Rapid Labeling**: Best for small teams or rapid prototyping.
- **Test Batch**: Ideal for large teams or gold-standard labeling.
- **Tiered Labeling**: Recommended for segmentation tasks, with multiple review stages.
- **Consensus Labeling**: Effective for less time-intensive tasks (e.g., bounding boxes).

---

![Flowchart](images/flowchart.png)

---
