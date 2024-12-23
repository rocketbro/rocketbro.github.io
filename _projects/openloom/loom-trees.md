---
layout: project
nav_title: "Loom Trees"
project_title: "OpenLoom"
description: "Defining a Loom Tree"
order: 3
---

On this page, we'll define a *loom tree* - a non-linear conversational exchange composed of [nodes](/projects/openloom/nodes/). Loom trees always have a single root node, and can have any number of child nodes. Bookmarked nodes are also tracked at the tree level, letting users quickly jump back to an important point in the exchange.

### Loom Tree Structure
```typescript
// typescript
// OpenLoom Version 1.0

type LoomTree = {
    id: string; // Unique identifier for the tree
    title: string; // Title of the tree
    description: string | null; // Description of the tree (optional)
    lastModified: Date; // Last modification date of the tree

    systemMessage: string; // System message for the tree
    rootNodeId: string; // ID of the tree's root node
    currentNodeId: string; // ID of the current node in the exchange, i.e. the latest message on the current branch
    nodes: { [key: string]: OpenLoomNode }; // Map of node IDs to OpenLoomNodes for all nodes in the tree
    bookmarkedNodes: { [key: string]: OpenLoomNode }; // Map of node IDs to OpenLoomNodes for bookmarked nodes
}
```
### Sharing Trees

In order to make OpenLoom and loom trees as useful as possible to others, it's good practice to provide a description of the tree. This can be as simple as *"A brief conversation about the meaning of life"* or something much more in depth; the general idea is to try to give some idea of what the tree contains.

### Navigating The Tree
Below, you can see an example implementation of a function to get all the relevant nodes for a branch of the conversation. This would be defined as a method on the `LoomTree` class, and also handles updating the tree's current node property appropriately. This method makes it easy to regularly update the UI of an interface to only show nodes that are relevant to the current branch. To get the conversation preceeding a given node, simply call the method with that node as the `input_node`. To trace the conversation branch forward to the latest message (for example, when the node in question is *not* the latest message), you would set the `trace_children` parameter to `true`.

```python
# python
# OpenLoom Version 1.0

def load_nodes(input_node=None, trace_children=False):
    # If no input node is provided, use the current node of the tree
    input_node = input_node or self.current_node

    # node_cache will eventually contain all
    # the nodes to be displayed to the user
    node_cache = [input_node]

    # Use the parent property of a node
    # to retrace the conversation backward
    # from the input_node to the root of
    # the conversation.
    
    current_node = input_node
    while current_node.parent is not None:
        # Insert the parent node at the beginning of the node_cache array
        node_cache.insert(0, current_node.parent)

        # Set the remembered_child property of the parent node to the current node
        current_node.parent.remembered_child = current_node

        # Move to the parent node
        current_node = current_node.parent

    # At this point, node_cache contains
    # all nodes preceding the input_node,
    # as well as the input_node itself at
    # the end index.

    if trace_children:
        # Use the remembered_child property of a node
        # to rebuild the conversation branch to the
        # latest message.
        
        current_node = input_node
        while current_node.remembered_child is not None:
            # Insert the remembered child node at the end of the node_cache array
            node_cache.append(current_node.remembered_child)

            # Move to the remembered child node
            current_node = current_node.remembered_child

        # node_cache now contains as many children
        # as can be traced, and current_node is equal to
        # the last message in the array.

        # Set the current node of the tree to the last message
        self.current_node = current_node

    else:
        # If trace_children is false, set the tree's
        # current_node to the input_node, since that
        # will be the latest message in the exchange.

        self.current_node = input_node

    # Finally, return the ordered list.
    return node_cache
```

### Example Loom Tree

Download this example loom tree to see the OpenLoomspec in action.

{% include download-button.html 
  file="/dlc/loom-interface/24-12-15 The Existence of Claude.openloom.json" 
  name="The Existence of Claude" 
  type="OpenLoom JSON File" 
%}

