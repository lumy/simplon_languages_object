
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

Write thebtree_apply_prefixfunction, which executes the function given as parameter to each node while imple-menting a pre-order tree traversal. It must be prototyped as follows:voidb t r e e _ a p p l y _ p r e f i x ( b t r e e _ t*r o o t ,i n t(*a p p l y f ) (void*) ) ;Delivery:CPool_Day13_$ACADEMICYEAR/btree_apply_prefix.c2
Task03btree_apply_infixWrite thebtree_apply_infixfunction, which executes the function given as parameter to each node, while imple-menting an in-order tree traversal. It must be prototyped as follows:voidb t r e e _ a p p l y _ i n f i x ( b t r e e _ t*r o o t ,i n t(*a p p l y f ) (void*) ) ;Delivery:CPool_Day13_$ACADEMICYEAR/btree_apply_infix.cTask04btree_apply_suffixWrite thebtree_apply_suffixfunction, which executes the function given as parameter to each node, while imple-menting a post-order tree traversal. It must be prototyped as follows:voidb t r e e _ a p p l y _ s u f f i x ( b t r e e _ t*r o o t ,i n t(*a p p l y f ) (void*) ) ;Delivery:CPool_Day13_$ACADEMICYEAR/btree_apply_suffix.cTask05btree_insert_dataWrite thebtree_insert_datafunction that inserts the item element into a tree.The tree given as parameter must be sorted, which means that for eachnode, all lower elements must be in the leftsubtree and all greater than/equal to elements must be in the right subtree.You will give a comparative function as parameter, which acts the same way asstrcmp.It must be prototyped as follows:voidb t r e e _ i n s e r t _ d a t a ( b t r e e _ t**r o o t ,void*item ,i n t(*cmpf ) ( ) ) ;Delivery:CPool_Day13_$ACADEMICYEAR/btree_insert_data.c3
Task06btree_search_itemWrite thebtree_search_itemfunction that returns the first element that corresponds to the reference data given asparameter. If the element is not found, the function must returnNULL. You must implement an infix tree search.It must be prototyped as follows:void*b t r e e _ s e a r c h _ i t e m ( b t r e e _ tc o n s t*r o o t ,void  c o n s t*d a t a _ r e f ,i n t(*cmpf ) ( ) ) ;Delivery:CPool_Day13_$ACADEMICYEAR/btree_search_item.cTask07btree_level_countWrite thebtree_level_countfunction that returns the size of the biggest branch given as parameter.  It must beprototyped as follows:s i z e _ t   b t r e e _ l e v e l _ c o u n t ( b t r e e _ tc o n s t*r o o t ) ;Delivery:CPool_Day13_$ACADEMICYEAR/btree_level_count.cFor instance, in the following example, the size of the biggest branch is 5:GoodluckforgreatdaythisofCpoolThe typesize_tis defined instddef.h.4
Task08btree_apply_by_levelWrite thebtree_apply_by_levelfunction, which executes the function given as parameter to each node in the tree.A level-by-level tree search should be implemented. The called function should have the three following parameters:•the node’s item (void*)•the current position’s level (int): 0 for root, 1 for children, 2 for subtrees•1 if it is the first level, 0 otherwise (int)It must be prototyped as follows:voidb t r e e _ a p p l y _ b y _ l e v e l ( b t r e e _ t*r o o t ,void(*a p p l y f ) (void*item ,i n tl e v e l ,i n ti s _ f i r s t _ e l e m ) )Delivery:CPool_Day13_$ACADEMICYEAR/btree_apply_by_level.cFor instance, for a tree like the one represented above, theapplyffunction should be called separately, using thefollowing parameters:•"Good", 0, 1•"Luck", 1, 1•"for", 2, 1•"this", 2, 0•"great", 3, 1•"day", 3, 0•"of", 3, 0•"C", 4, 1•"pool", 4, 05
Task09rb_insertFor the last two tasks, we are going to work with red-black trees:typedef  s t r u c trb_node{s t r u c trb_node*l e f t ;s t r u c trb_node*r i g h t ;void*d a t a ;enumRB_COLOR  { RB_BLACK ,  RB_RED }   c o l o r ;}  rb_node_t ;Add this structure in your btree.h file.This structure has the same properties as the structure found at the beginning. It’s possible to reuse the functions thatyou have already written for red-black trees. Think of it as a basic form of polymorphism in C.If you think it’s necessary, you may add some properties at the end of therb_node_tstructure.29742181115206946375380747586Write therb_insertfunction, which adds new data to the tree while simultaneously keeping the red-black tree’s re-strictions.Therootparameter points to the tree’ s root node.During the first call, it may be set to aNULLpointer.You also need a comparative function that acts the same way asstrcmpIt must be prototyped as follows:voidr b _ i n s e r t ( rb_node_t**r o o t ,void*data ,i n t(*cmpf ) ( ) ) ;Delivery:CPool_Day13_$ACADEMICYEAR/rb_insert.c6
Task10rb_removeWrite therb_removefunction, which deletes data from the tree while simultaneously keeping the red-black tree’srestrictions.Therootparameter points to the tree’s root node.You also need a comparative function that acts the same way asstrcmp.A function pointer calledfmust be called with the tree’s elements that must be deleted.It must be prototyped as follows:voidrb_remove ( rb_node_t**r o o t ,void*data ,i n t(*cmpf )   (void*,void*) ,void(*f )   (void*) ) ;Delivery:CPool_Day13_$ACADEMICYEAR/rb_remove.c
