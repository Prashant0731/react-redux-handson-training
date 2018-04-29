# Contents

* [User Story](#user-story)
* [Code Snippet](#code-snippet)

## User Story
- There should be a way to create delete button
- There should be a delete button for each issue
- Each li should have an id that has the issue position
- Delete button should have access to the issue id
- Clicking delete should update issueList.issues and DOM

## Code Snippet

### There should be a way to create delete button
```
var view = {
    displayIssue :  function(){
       --------
       --------        
    },    
    createDeleteButton: function () {
        var deleteButton;
        deleteButton =  document.createElement('button');
        deleteButton.textContent = 'Delete';
        deleteButton.className = 'deleteIssue';
        return deleteButton;
    }
};

Note :  Call view.createDeleteButton(); on browser console.
```

### There should be a delete button for each issue
```
Note :  Call createDeleteButton while adding issueLi. button should be created at the time of issue display.

var view = {
    displayIssue :  function(){
       -------------------------------------
            issueLi.textContent = issueTextWithCompletion;
            issueLi.appendChild(this.createDeleteButton()); // call createDeleteButton and appending as a child node in issueList
            issueUl.appendChild(issueLi);
        }
        
    }
```

### Each li should have an id that has the issue position
```
Note :  For assigning id to each list item. We can add id attribute to issueLi, that id attribute will have id value from loop iteration.
var view = {
    displayIssue :  function(){
       -------------------------------------
            issueLi.id = i; // adding id that is received from the iteration
            issueLi.textContent = issueTextWithCompletion;
            issueLi.appendChild(this.createDeleteButton()); // call createDeleteButton and appending as a child node in issueList
            issueUl.appendChild(issueLi);
        }
        
    }
```

### Delete button should have access to the issue id
```
var issuesUl =  document.querySelector('ul');
issuesUl.addEventListener('click',function(event){
    console.log(event.target.parentNode.id);
});

Note : 
Target :  target property that tells about the target clicked. 
parentNode :  li is the parent node in this case
id: id is the attribute of li

```

### Clicking delete should update issueList.issues and DOM
````
var issuesUl =  document.querySelector('ul');
issuesUl.addEventListener('click',function(event){
    // get the target element that is clicked
    var elementClicked =  event.target;
    // check if element clicked is deleteIssue button
    if(elementClicked.className === 'deleteIssue'){
        // call handlers deleteIssue method
        handlers.deleteIssue(parseInt(elementClicked.parentNode.id));
    }
    console.log(event.target.parentNode.id);
});

Note :  change the handlers.deleteIssue () method

 deleteIssue:function(position){
        //var deleteIssuePositionInput=document.getElementById('deleteIssuePositionInput');
        issueList.deleteIssue(position);
        view.displayIssue();
       // deleteIssuePositionInput.value='';
    }
````

