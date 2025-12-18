
The union is similar to a structure. Except all its components share a memory. It can be used to store either a number or an operator in the same place in the memory.
The enum is enumeration. It assigns a natural$_0$ number to every entry.
```c
typedef enum {
	ADD,
	MUL,
	DIV,
	SUB
} operation_t;

...

union {
	operation_t m_operation;
	int m_value;
} m_data;
```


To free a binary tree.
```c
void free_nodes(node_t * node) {
	if (!node) return;
	
	free_nodes(node->left);
	free_nodes(node->right);
	
	free(node);
}
```

To validate a binary search tree, do in order traversal and see if the values are increasing. ($\geq$)

