<!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# Microsoft 365 CLI - TODO Commands Reference

*This is an automatically generated condensed reference of all TODO commands for the Microsoft 365 CLI, optimized for LLMs.*

*Generated on: 2025-08-01*

---

## Table of Contents

- [list-add](#list-add)
- [list-get](#list-get)
- [list-list](#list-list)
- [list-remove](#list-remove)
- [list-set](#list-set)
- [task-add](#task-add)
- [task-get](#task-get)
- [task-list](#task-list)
- [task-remove](#task-remove)
- [task-set](#task-set)

---

## list-add

### Syntax
```
m365 todo list add [options]
```

### Example
```
m365 todo list add --name "My task list"

```

---

## list-get

### Syntax
```
m365 todo list get [options]
```

### Example
```
m365 todo list get --id "EXAMPLE_SECRET_VALUE_PLACEHOLDER="

m365 todo list get --name "Task list"

```

---

## list-list

### Syntax
```
m365 todo list list [options]
```

### Example
```
m365 todo list list

```

---

## list-remove

### Syntax
```
m365 todo list remove [options]
```

### Example
```
m365 todo list remove --name "My task list"

m365 todo list remove --id "EXAMPLE_SECRET_VALUE_PLACEHOLDER=" --force

```

---

## list-set

### Syntax
```
m365 todo list set [options]
```

### Example
```
m365 todo list set --id "EXAMPLE_SECRET_VALUE_PLACEHOLDER=" --newName "My updated task list"

m365 todo list set --name "My Task list" --newName "My updated task list"

```

---

## task-add

### Syntax
```
m365 todo task add [options]
```

### Example
```
m365 todo task add --title "New task" --listName "My task list"```

### Remarks
When you specify the values for `categories`, each category can correspond to the displayName property of an [outlookCategory](https://learn.microsoft.com/graph/api/resources/outlookcategory?view=graph-rest-1.0). It is permissible to use distinct names.



---

## task-get

### Syntax
```
m365 todo task get [options]
```

### Example
```
m365 todo task get --listName "My task list" --id "EXAMPLE_SECRET_VALUE_PLACEHOLDER="

m365 todo task get --listId "EXAMPLE_SECRET_VALUE_PLACEHOLDER==" --id "EXAMPLE_SECRET_VALUE_PLACEHOLDER="

```

---

## task-list

### Syntax
```
m365 todo task list [options]
```

### Example
```
m365 todo task list --listName "My task list"

m365 todo task list --listId "EXAMPLE_SECRET_VALUE_PLACEHOLDER=="

```

---

## task-remove

### Syntax
```
m365 todo task remove [options]
```

### Example
```
m365 todo task remove --id "EXAMPLE_SECRET_VALUE_PLACEHOLDER=" --listName "Tasks"

m365 todo task remove --id "EXAMPLE_SECRET_VALUE_PLACEHOLDER=" --listId "EXAMPLE_SECRET_VALUE_PLACEHOLDER="

```

---

## task-set

### Syntax
```
m365 todo task set [options]
```

### Example
```
m365 todo task set --id "EXAMPLE_SECRET_VALUE_PLACEHOLDER=" --title "Update doco" --listName "My task list"```

### Remarks
When you specify the values for `categories`, each category can correspond to the displayName property of an [outlookCategory](https://learn.microsoft.com/graph/api/resources/outlookcategory?view=graph-rest-1.0). It is permissible to use distinct names.



---
