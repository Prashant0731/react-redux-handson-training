# Contents

* [User Story](#user-story)
* [Code Snippet](#code-snippet)

## User Story
- There should be a li element for every issue
- Each li element should contain issueText
- Each li element should show the completed

## Code Snippet
```
var view = {
    displayIssues :  function () {
        var issueUl = document.querySelector('ul');
        issueUl.innerHTML = '';
        
        for(var i=0; i<issueList.issues.length;i++){
            var issueLi = document.createElement('li');
            var issue = issueList.issues[i];
            var issueTextWithCompletion = '';
            if(issue.completed === true){
                issueTextWithCompletion = '(X)'+issue.issueText;
            }
            else{
                issueTextWithCompletion = '()'+issue.issueText;
            }
            issueLi.textContent = issueTextWithCompletion;
            issueUl.appendChild(issueLi);
        }
        
    }
};

```
Note :  call view.displayIssues() method in addIssues() method of handlers object and call in all other methods as well. 
For more detail watch vedio on : 
