
# Note:

This subject was wrote for C/C++ exercices, the syntax for structure, function (etc...) might not be
the same as in your language, you will have to adapt the exercices to your languages, in case of
double ask *Lumy* about it.

# Cat

Write a program called cat, which executes the same tasks as your system’s cat command. You do
not have to handle options. There is an unlimited number of files given as parameter.
cat without parameters must be supported.

You have to give a readme explaining how to compile
The binary’s name must be `cat`.

# Grep

Write a program called grep, which executes the same tasks as your system’s `grep` command. You
do not have to handle options. There is an unlimited number of files given as parameter.
You have to give a readme explaining how to compile
The binary’s name must be `grep`.

# Binary Tree

For today’s tasks, we will be using the following structure:
```
typedef  struct btree {
  struct btree* left;
  struct btree* right;
  void*  item;
}  btree_t;
```

0.Don’t forget to write unit tests for all your functions!

## Task01 btree_create_node

Write the tree_create_node function, which allocates a new node and initializes its item to the parameter value (and all the others to 0).
The newly-created node’s memory address must be returned (return the instance or a reference of the instance).
It must be prototyped as follows: `btree_t* btree_create_node(void* item);`

## Task02 btree_apply_prefix

Write the `btree_apply_prefix` function, which executes the function given as parameter to each node
while implementing a pre-order tree traversal.
It must be prototyped as follows: `void btree_apply_prefix(btree_t* root , int (*applyf) (void*) );`


## Task03 btree_apply_infix

Write the `btree_apply_infix` function, which executes the function given as parameter to each node,
while implementing an in-order tree traversal. It must be prototyped as follows: `voidb
tree_apply_infix(btree_t* root , int (*applyf) (void*) );`

# Task04 btree_apply_suffix

Write the `btree_apply_suffix` function, which executes the function given as parameter to each
node, while implementing a post-order tree traversal.
It must be prototyped as follows: `voidb tree_apply_suffix(btree_t* root, int(*applyf) (void*) ) ;`

## Task05 btree_insert_data

Write the `btree_insert_data` function that inserts the item element into a tree. The tree given as
parameter must be sorted, which means that for each node, all lower elements must be in the left
subtree and all greater than/equal to elements must be in the right subtree.
You will give a comparative function as parameter, which acts the same way as strcmp.
It must be prototyped as follows: `void btree_insert_data(btree_t **root, void* item , int(*cmpf ) ())`

## Task06 btree_search_item

Write the `btree_search_item` function that returns the first element that corresponds to the
reference data given as parameter. If the element is not found, the function must return NULL.
You must implement an infix tree search.
It must be prototyped as follows:
`void *btree_search_item(btree_t const *root, void const* data_ref, int(*cmpf ) ( ) );`

## Task07 btree_level_count

Write the `btree_level_count` function that returns the size of the biggest branch given as
parameter.  It must be prototyped as follows:
`size_t btree_level_count(btree_t const* root);`

## Task08 btree_apply_by_level

Write the `btree_apply_by_level` function, which executes the function given as parameter to each
node in the tree.
A level-by-level tree search should be implemented. The called function should have the three
following parameters:
  - the node’s item (void*)
  - the current position’s level (int): 0 for root, 1 for children, 2 for subtrees
  - 1 if it is the first level, 0 otherwise (int)

It must be prototyped as follows:
`void btree_apply_by_level(btree_t* root, void(*applyf) (void* item, int level, int is_first_elem))`
