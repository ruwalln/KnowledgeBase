# Oracle APEX Code JavaScript / CSS3

## JavaScript programming Form execution

### APEX update a selected ROW in InteractiveGrid after updating Data in a Form without reloading

You are able to refresh a selected row after update data in a single form after closing the form. Normally the data would not be updated automatically without a refresh of the whole classic grid form. Therefor you are able to use JavaScript to do the whole job. Here is an example how to  use the JavaScript funtions. The Functions belongs to :

apex.region("region-id").widget.interactive_grid("get-actions").invoke("action-name");

Requirements: 

The updated region must be a single selected row which has an unique static ID like "AlternateRowIG". In this case its a row using an alternative coloring by JavaScript.
In the Page Designer define a "Dynamic Action" -> DialogClosed <- to Check a Form has been Closed after updating a specific row.



In the Properties define the following values :
| Dynamic Action | Properties |
| -------------- | ---------- |
| ![image](https://github.com/user-attachments/assets/79a74a71-c858-41b9-82b8-a8903e46108d) | ![image](https://github.com/user-attachments/assets/90572755-5f9a-4627-9d4f-59b25a481410) | 
|   |  |

In the "True" Section define the following JavaScript Segment:

```
	// make sure it is the dialog we are expecting that closed
	if ( this.data.dialogPageId  === 6 ) {
		if ( this.data.successMessage ) {
			// use this API to show the success message if any that came from the dialog
			apex.message.showPageSuccess(this.data.successMessage.text);
		}
		// refresh the region to pick up any changes made by the dialog that just closed
        // emp ist hier die Statische ID des Interactive Grids 
        
		apex.region("AlternateRowIG").widget().interactiveGrid("getActions").invoke("selection-refresh");
        
        // apex.region ("emp").widget ().interactiveGrid ("getActions").invoke ("selection-refresh")
        // apex.region("emp").widget().interactiveGrid("getActions").invoke("save");
	}
```

Here is a list of actions that can be invoke from APEX using JavaScript programming.

| Name	                                 | Type	        | Description |
| -------------------------------------- | ------------ | ----------- | 
| search	| Action	| Handles the main search functionality available from the search field in the toolbar.| 
| search-case-sensitive	| Toggle	| Toggle whether the search is case-sensitive.| 
| filter-column	| Radio	| Constrain search to a specific column.| 
| change-report	| Radio	| Switch to a different saved report.| 
| change-view	| Action	| Switch to a different view (eg grid, icon, detail, etc.).| 
| chart-view	| Action	| Switch to the chart view. Note: This is handled differently to other views because this is user-defined and may not be configured.| 
| show-columns-dialog	| Action	| Show the columns dialog.| 
| show-filter-dialog	| Action	| Show the filter dialog.| 
| show-sort-dialog	| Action	| Show the sort dialog.| 
| show-aggregate-dialog| 	Action	| Show the aggregate dialog.| 
| show-flashback-dialog	| Action	| Show the flashback dialog.| 
| show-highlight-dialog	| Action	| Show the highlight dialog.| 
| show-control-break-dialog| 	Action| 	Show the control break dialog.| 
| show-download-dialog| 	Action	| Show the download dialog.| 
| show-help-dialog	| Action	| Show the help dialog.| 
| stretch-columns	| Toggle	| Toggle if columns are set to stretch to their available width (for views that support it).| 
| change-rows-per-page	| Radio	| Set the number of grid rows displayed for the current page.| 
| save-report	| Action	| Save the current report settings.| 
| show-save-report-as-dialog| 	Action| 	Show the 'Save Report As' dialog.| 
| show-edit-report-dialog	| Action| 	Show the 'Edit Report' dialog.| 
| delete-report	| Action	| Delete the current saved report.| 
| reset-report	| Action	| Reset the current report settings.| 
| row-add-row	| Action	| Insert a row straight after the current row.| 
| row-duplicate	| Action	| Duplicate the current row.| 
| row-delete	| Action	| Delete the current row.| 
| row-refresh	| Action	| Refresh the current row.| 
| row-revert	| Action| 	Revert the current row to its original state when the Interactive Grid region was refreshed.| 
| selection-mode	| Toggle	| Toggle the current selection mode (true for row selection, false for cell selection).| 
| selection-duplicate	| Action| 	Duplicate the current selected rows. Note: Interactive Grid must be editable.| 
| selection-delete	| Action	| Delete the current selected rows. Note: Interactive Grid must be editable.| 
| selection-refresh	| Action| 	Refresh the current selected rows from the server. Note: Interactive Grid must be editable.| 
| selection-revert	| Action	| Revert the current selected rows to their original state when the Interactive Grid region was refreshed. Note: Interactive Grid must be editable.| 
| selection-copy	| Action	| Copy the current selection to the clipboard. Note: Interactive Grid must be editable.|
| selection-add-row	| Action	| Insert a row straight after any selected rows. If no rows are selected, or if cell selection mode is enabled, the new row will be added at the beginning.| 
| selection-copy-down	| Action	| Copy cell values from columns in the first selected row to all the other selected rows within the same columns. Note: Interactive Grid must be editable, and only supported in 'Grid' view.| 
| selection-clear	| Action	| Clear all cells in the current selection. Note: Interactive Grid must be editable, and only supported in 'Grid' view.| 
| selection-fill	| Action	| Fill all cells in the current selection with the value provided. Note: Interactive Grid must be editable, and only supported in 'Grid' view.| 
| refresh	| Action	| Refresh the Interactive Grid region.| 
| edit	| Toggle	| Toggle | the current edit mode.| 
| save	| Action	| Save the current data changes. Note: Interactive Grid must be editable.| 
| single-row-view	| Action	| Change to single row view. Note: The current view must support single row view.| 
| close-single-row-view	| Action	| Change from single row view. Note: The current view must support single row view.| 


### using Theme Roller and User Custom CSS for the application

Using the Custom User CSS you are able to customize form items in your application. For example using big 24 letters in a field using a single CSS line of information.

![image](https://github.com/user-attachments/assets/3821b87d-a789-4cf7-a6bc-b3e80a91f6c1)

Using this line of CSS in the CSS-Class Section of the TextField Item.

big-24-input

![image](https://github.com/user-attachments/assets/e7904def-75dd-4f74-b4ce-014adaed6c79)

Here you can see the single CSS script lines todo the whole job.

```
.big24-input {
  background-color: rgb(250, 249, 249);
  color: rgb(2, 2, 2);
  height: 85px;
  font-size: 45px;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;  
  box-shadow: inset 1px 1px 2px 0px #E2E2E2;
  border-radius: 8px;    
}
```



```
/* Custom CSS for Rounded Buttons */
.rounded-button {
    border-radius: 5px; /* Adjust the value for more or less rounding */
    padding: 15px 30px; /* Adjust padding for desired button size */
    background-color: rgb(235, 235, 235); /* Button background color */
    color: rgb(0, 0, 0); /* Button text color */
    border: none; /* Remove default border */
    cursor: pointer; /* Pointer cursor on hover */
    transition: background-color 0.3s ease; /* Smooth transition for hover effect */
}

.rounded-button:hover {
    background-color: rgb(0, 0, 0);/* Darker shade on hover */
    color: rgb(255, 255, 255);
}

/* Custom Input Textarea Fields */

.rounded-textarea {
  font-size: 16px;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  box-shadow: inset 1px 1px 2px 0px #E2E2E2;
  background-color: rgb(248, 248, 246);
  border-radius: 8px;
  //border-width: 1px;
  border-color: rgb(240, 237, 237);
}

.rounded-textarea:focus {
  box-shadow: inset 1px 1px 2px 0px #E2E2E2;
  background-color: rgb(253, 253, 253);
  border-radius: 8px;
  //border-width: 1px;
  //border-color: rgb(202, 201, 204);
}

.rounded-textarea:hover {
  box-shadow: inset 1px 1px 2px 0px #E2E2E2;
  background-color: rgb(255, 255, 255);
  border-radius: 8px;
  //border-width: 1px;
  //border-color: rgb(202, 201, 204);
}

.rounded-input[type=text]:focus {
  font-size: 16px;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background-color: rgb(255, 254, 254);
  border-radius: 8px;
}

.rounded-input[type=text] {
  font-size: 16px;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;  
  box-shadow: inset 1px 1px 2px 0px #E2E2E2;
  border-radius: 8px;
}

.rounded-selectlist:focus {
  font-size: 16px;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background-color: rgb(255, 254, 254);
  border-radius: 8px;
}

.rounded-selectlist {
  height: 53px;
  font-size: 16px;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;  
  box-shadow: inset 1px 1px 2px 0px #E2E2E2;
  border-radius: 8px;    
}

.big24-input {
  background-color: rgb(250, 249, 249);
  color: rgb(2, 2, 2);
  height: 85px;
  font-size: 45px;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;  
  box-shadow: inset 1px 1px 2px 0px #E2E2E2;
  border-radius: 8px;    
}

```
