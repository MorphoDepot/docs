# Community Guidelines for MorphoDepot Archival Datasets

This is a starting guide for labs and researchers who want to join the MorphoDepot organization.

> Status: DRAFT. This reworks the archival overview into onboarding guidelines for new org members. Some headings here are meant to be linked from the Slicer extension.

---

## MorphoDepot is for annotated anatomy, not raw scans

Read this part first. It frames everything else.

A scan is where a dataset starts. It is not the dataset itself. The real content is the segmentation. You identify anatomical structures. You name them with real terminology. The community refines them over time. MorphoDepot is a home for annotated anatomy.

We are not building another MorphoSource. Scan archives like MorphoSource already store and share raw scans. MorphoDepot does not repeat that job. You can share a bare scan here so others can start working on it. But a bare scan is not the goal. A bare scan on its own never gets a DOI. The citable object is the annotated dataset that grows on top of the scan.

If you only want to deposit a scan, use a scan archive. If you want to build, label, and share anatomy together, this organization is for you.

---

## Two kinds of dataset

You choose the dataset type when you create it. The choice is permanent.

| | Short-term | Archival (this guide) |
|---|---|---|
| Who can create | anyone | org members only |
| Where it lives | your personal GitHub account | the MorphoDepot organization |
| Storage for the scan | GitHub attachment, up to 2 GB | Jetstream2 cloud storage, 10 GB by default, up to 1 TB, with off-site backup |
| Citable (DOI) | no | yes |
| Governance | yours alone, delete anytime | community-governed |
| Best for | teaching, drafts, experiments | lasting, citable datasets |

The two types never cross. There are no citable personal datasets. There are no disposable organization datasets. Membership unlocks the archival type. It does not force it. As a member you can still make short-term datasets for casual or classroom work.

The rest of this guide is about archival datasets.

---

## Joining the organization

Lab PIs join at [join.morphodepot.org](https://join.morphodepot.org). You sign in with your ORCID iD. You confirm your email. The app then adds you to the organization and creates your personal team. ORCID sign-in lets the platform credit you automatically. It also ties that credit to your verified identity. See "What you get back" below.

Joining means joining a shared, governed space. It is not a private sandbox. The sections below explain what that means.

---

## Work in the open as a community

People here work together in public. A few habits matter.

**Mention people directly.** In an issue or a pull request, type @ and their handle. Use it to ask a question. Use it to request a second opinion on a hard region. Use it to hand off a structure. Use it to credit a contributor. These conversations are public. They are attributed by default.

**Use Discussions for talk and Issues for work.** Open a Discussion in the organization for open-ended topics. Examples are a new terminology, a color convention, a workflow idea, or a call for collaborators. Open an Issue for concrete work on one dataset. Examples are a segmentation task to assign, a problem to fix, or a release to plan. Discussions are for talking. Issues are for doing.

**Build terminologies and color tables together.** The terms and colors you segment with are a shared resource. Do not reinvent them in each lab. Start from the shared set. Contribute back to it. Propose additions to it.

- [SlicerMorph/terms-and-colors](https://github.com/SlicerMorph/terms-and-colors) is the shared library of anatomical terminologies and color tables.
- The [colors and terms tutorial](https://github.com/SlicerMorph/Tutorials/tree/main/Segmentation/colors-and-terms) shows how to build, edit, and apply a terminology color table in 3D Slicer.

If your group segments something the shared set does not cover, open a Discussion and a pull request to terms-and-colors. Do not keep it in a private file. That is how the resource grows.

---

## What changes when your data lives in the organization

An archival dataset is a shared resource under joint stewardship. That brings trade-offs that a personal repository does not have. Know them before you join.

**It is a one-way door.** While a dataset is still private and staged, you can discard it freely. Once you publish a dataset, you cannot quietly delete or hide it. Removing a published dataset is an organization action. The curator cannot do it alone. You are making a durable commitment. That commitment is what makes a DOI meaningful.

**Publishing passes a short editorial check.** Think of a journal's handling editor. That editor confirms a submission is in good order before it is published. The editor is not a peer reviewer judging the science. The editor confirms the dataset is well-formed. It has a real specimen and a real name. It uses recognized terminology. It has a license. The scan opens and is what it claims to be. The editor does not rule on whether a segmentation is anatomically perfect. This follows the spirit of the PLOS ONE model. The check is for validity and soundness. It does not judge the importance of the result.

**Accuracy is the community's job, and it improves over time.** Publishing certifies that a dataset is sound and usable. It does not certify that the dataset is finished. If a segmentation can be improved, contributors correct and extend it. That is the point.

If you want full control and the ability to delete at any time, use a short-term personal dataset. Archival means shared.

---

## What an archival dataset must have

These are requirements. The app checks them automatically when you publish a dataset or make a release. It re-runs the checks on your latest commit. A hard failure sends the request straight back to you with a list of fixes. No reviewer is involved. A soft finding does not block. It is flagged for the editor to look at. Design your dataset to meet these from the start. That avoids round-trips.

### Name it for the specimen

Use a descriptive name based on the specimen. The pattern is Genus-species plus what is in the dataset. A good example is Ariopsis-felis-cranium. Do not use names like my-repo, project1, or test123. The name is permanent and public. It is how others find and cite the dataset. An automatic naming check is not in place yet. Until it is, the editor checks the name during review.

### Segment with real terminology

This is the core requirement. It is enforced in two places.

At creation, a generic or default 3D Slicer color table is rejected. You must load a real terminology color table. The terms-and-colors library is the place to get one.

At publish, three hard checks apply. The color table must be a terminology table with populated ontology codes for Category, Type, and Region. It cannot be a plain or continuous color map. Every segment must be named from that table. Segment names must be unique.

Names like Segment_1, or 1, 2, 3, or other ad-hoc labels will not pass. Each structure must carry a recognized anatomical name that exists in your terminology table. There is one soft case. A table where every entry falls back to the generic "Tissue" placeholder is allowed, but it is flagged for the editor. If you truly have no standard ontology for a structure, that is fine. It is still worth a second look. The colors and terms tutorial shows how to build a table properly.

### Describe a real specimen

At creation you fill a short accession form. It records the species, the specimen type, the sex, the developmental stage, the acquisition modality, and the anatomical regions. If the specimen is accessioned, it also records the iDigBio record. At publish, the species is checked against GBIF as a soft check. Any iDigBio URL is resolved as a soft check. Real, resolvable specimen metadata is what makes the dataset useful and citable.

### Set a correct voxel size in millimeters

The scan must record an accurate voxel size in millimeters. The voxel size sets the real-world scale of the specimen. The reviewer checks that this scale is physically plausible. For example, a bee scanned at 1.0 mm per voxel over 2000 slices would describe a specimen about two meters long. That scale is wrong, and it will not pass review. Many scans are acquired in microns, so convert before you set it. A 10 micron voxel is 0.010 mm. Set the voxel size correctly in 3D Slicer before you create the dataset.

### Build any baseline on the source volume

A dataset may publish as a bare scan with no segmentation. This lets the community start on it. If you do include a baseline segmentation, it must be built on the dataset's own source volume. Its reference geometry must match the scan's dimensions. This is a hard check. The baseline's segments must also follow the terminology rules above.

### Provide a license and a screenshot

Choose a license when you create the dataset. The options are CC BY 4.0 and CC BY-NC 4.0. Include at least one screenshot of the dataset. Having a screenshot is a hard check. The screenshot must show the data. If the dataset has a segmentation, the screenshot must show that too. The reviewer checks this, so a blank or unrelated image will not pass. A good screenshot lets reviewers and readers see what the dataset is at a glance.

---

## What you get back


**You get automatic credit.** No need to track who did what. When a curator accepts and merges an issue, the contributor is credited automatically at the next (and subsequent) release. Contibutions by non-org members are credited by GitHub handle only, although repo curator manually can edit their information.  Org members are  credited by their verified ORCID name and affiliation. The curator who created the dataset and the repo and responsible for review the segmentations is the lead author by default. 

**Your releases get citable DOIs.** A dataset becomes citable at its first release that contains a segmentation. Each release gets its own version DOI. There is also one concept DOI that always resolves to the latest version. Both are minted through Zenodo. Both appear on the dataset's front page README.md automatically with a ready-to-paste citation. T

**Larger volume sizes are supported.** The source scan lives in dedicated cloud object storage and is not subject to 2GB GitHub release asset limit. Currently volume file is capped at 10 GB for practical segmentation reasons (you typically need 6-10 times more memory compared to the volume size). Although existing infrastructure can handle datasets 100sGB of in size. 

---

## Where to go next

- [join.morphodepot.org](https://join.morphodepot.org) onboards your lab with ORCID.
- [SlicerMorph/terms-and-colors](https://github.com/SlicerMorph/terms-and-colors) is the shared terminology and color-table library to start from and contribute to.
- The [colors and terms tutorial](https://github.com/SlicerMorph/Tutorials/tree/main/Segmentation/colors-and-terms) shows how to create and manage a terminology color table in 3D Slicer.
- The [MorphoDepot tutorial](https://github.com/SlicerMorph/Tutorials/tree/main/MorphoDepot) is a step-by-step guide to creating and operating MorphoDepot repositories.
- The organization's Discussions are where you introduce yourself, propose terminology, and find collaborators.
