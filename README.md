# Auto-annotations for the adult human brain
Computer-readable annotation for cell types and states in the adult human brain.

This resource has been produced for the work described in:

*Transcriptomic cell-type diversity across the adult human brain* </br>
Siletti et al. 2022


## Auto-annotation file format

Each label is defined in a yaml file with a short computer-readable section that contains four mandatory fields: name, abbreviation, definition and category.

```yaml
name: Oligodendrocyte precursor cell
abbreviation: OPC
definition: +SOX10 +PDGFRA
categories: Ectodermal 
```

The “abbreviation” and “name” are unique identifiers, whereas “categories” can be used to organize the labels into meta-labels. The “definition” is the most important field and represents the label-assignment rule. It consists of a list of gene names, each prefixed with “+” if the gene must be present or “-” if the gene must be absent. A cluster is assigned a label if and only if the “+” genes are present and the “-” genes are absent. Many different definitions for the same label are possible. To create robust labels that apply to diverse datasets, we favored definitions that comprised short lists of genes. 

Each document additionally contains a free-form section that is used to provide context, justification, and references for each annotation.


## How can I label cell types with auto-annotations?

The auto-annotation labels can be applied downstream of any method that determines "presence" or "absence" of a gene. Siletti et al. used the trinarization procedure implemented in Cytograph. 
