# Oracle APEX Code JavaScript / CSS3

## JavaScript programming Form execution

### APEX update ROW after updating Data in a Form without reloading

You are able to refresh a selected row after update data in a single form after closing the form. Normally the data would not be updated automatically without a refresh of the whole classic grid form. Therefor you are able to use JavaScript to do the whole job. Here is an example how to  use the JavaScript funtions. The Functions belong to :

apex.region("region-id").widget.interactive_grid("get-actions").invoke("action-name");

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
