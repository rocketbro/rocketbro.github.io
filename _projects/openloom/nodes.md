---
layout: project
nav_title: "Nodes"
project_title: "OpenLoom"
description: "Defining A Node"
order: 2
---

On this page, we'll define the structure of a single *node*. Nodes are the root level building blocks of a loom tree, and each represents a single message in a conversation. Nodes point to each other as parents and children to create the tree structure. `OpenLoom v1.0` only supports text-based nodes, but support for images and documents will be implemented in future versions.

### Node Structure
```typescript
// typescript
// OpenLoom Version 1.0

type Node = {
    id: string; // The id of the node
    text: string; // The text of the node
    author: Author; // The author of the node - see Author enum
    modelId: string; // Some identifier for the model used to generate the node
    createdTime: Date; // The time the node was created

    parentId: string | null; // The id of the parent node. Must only be null for the root node.
    childrenIds: string[]; // IDs of all children that claim this node as their parent
    rememberedChildId: string | null; // The id of the most recently visited child. Used to retrace branches.
}

enum Author { // A node must claim one of these cases as an author
    User = "user",
    Assistant = "assistant",
    System = "system"
}
```

Most properties are self-explanatory, but the `rememberedChildId` property requires a bit more explanation.

### Remembered Child
The `rememberedChildId` property is used to retrace conversation branches. It should be set to null by default, and updated the first time the user navigates to a child of that node. It should be subsequently updated whenever the user navigates to an alternate child, effectivley guaranteeing that it will always point to the most recently visited child.

This becomes useful when the user wants to trace a branch down as far as it goes, without having to reconstruct the branch manually, node by node. More on this in the [loom trees](/projects/openloom/loom-trees/) page.
