# Todo List API
This is a basic todo app API written in Java Spring Boot.

## USAGE
### GET
##### Get the names of all TODO lists
```java
GET /todo/v1/list
```
- Response: Set<String>
    ```json
    [
        "School",
        "Work",
        "PersonalProjects"
    ]
    ```

##### Get a TODO list by name
```
GET /todo/v1/list/{name}
```
- Response: com.todo.entity.TodoList
    ```json
    {
        "id": 1,
        "name": "School",
        "description": null,
        "todos": [
            {
                "id": 1,
                "name": "CSCD490 Sprint 2 DUE Friday 4/15",
                "description": null,
                "state": "incomplete",
                "todoListId": 1
            },
            {
                "id": 2,
                "name": "CSCD467 HW1 DUE Monday 4/18",
                "description": null,
                "state": "incomplete",
                "todoListId": 1
            }
        ]
    }
    ```

##### Get a TODO list item by ID
```
GET /todo/v1/{id}
```
- Response: com.todo.entity.TodoItem
    ```json
    {
        "id": 1,
        "name": "CSCD490 Sprint 2 DUE Friday 4/15",
        "description": null,
        "state": "incomplete",
        "todoListId": 1
    }
    ```
---

### POST

##### Create a new TODO list.
```
POST /todo/v1/list
```
- Request Body: com.todo.entity.TodoList
- Response: com.todo.entity.TodoList

##### Create a new TODO list item for the list with the provided name.
```
POST /todo/v1/list/{name}
```
- Request Body: com.todo.entity.TodoItem
- Response: com.todo.entity.TodoItem

---

### PUT

##### Update an existing TODO list item by its ID.
```
PUT /todo/v1/todo/{id}
```
- Request Body: com.todo.entity.TodoItem
- Response: com.todo.entity.TodoItem

---
### DELETE

##### Delete an existing TODO list item by its ID
```
DELETE /todo/v1/todo/{name}/delete
```

#### TODO
- [ ] Add due date property
- [ ] Add priority property