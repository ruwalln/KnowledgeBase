-- --------------------------------------
# ORACLE APEX 24.2 - Professional 2025
-- --------------------------------------

## Skill Checks

### 1 Getting Started with Oracle Apex on Autonomous Database

1. You can create an APEX workspace and build APEX apps on which of the follwing platforms ?

[ ] Oracle Autonomous Cloud
[ ] Oracle XE (free)
[ ] Amazon RDS
[ ] Microsoft Azure
[X] All of the above

2. Which three are the main components of APEX workspace homepage

[X] Gallery
[X] SQL Workshop
[X] App Builder
[ ] RESTful Services

3. Which two among the following are TRUE about Low Code Apps ?

[X] Provide Rich Functionality with Less Code
[ ] Expensive
[X] Scaleable
[ ] Not Mobile Friendly

4. Which two are true about Oracle APEX ?

[X] Is declaitive. It requires no code generation.
[ ] Performs the data processing in a middle tier server.
[ ] Requires developers to be proficient in Java, Python and other programming languages.
[X] Requires no additional client software. A web browser is the app development IDE.

### 2 Using SQL Workshop

1. Which component in SQL Workshop allows you to build queries graphically without manual SQL coding ?

[ ] Data Workshop
[X] Query Builder
[ ] SQL commands
[ ] Quick SQL

2. Using Data Workshop, you can perform which three tasks ?

[ ] Delete Data from the database.
[X] Load data using various such as XLXS, CSV, XML and JSON
[X] Load vast amount of data into the database.
[X] Export vast amount of data from the database into a file.

3. What three are the result of the following QuickSQL shorthand notation do?

departments /insert 4
	name /nn
	location
	country
	
[X] insert 4 rows of random data into the department table
[ ] Create the departments table with 3 columns
[X] Creates an id column as primary key
[X] Create the departments table with 4 columns

4. From SQL Workshop, you can perform which two following actions ?

[ ] Delete database
[X] Create and view database objects
[X] Run SQL commands and scripts
[ ] Create an APEX user

### 3 Creating a database application

1. Which three of the following options are TRUE about a page in an APEX application ?

[ ] An APEX application can have only one page.
[X] A page can contain buttons, page items and regions.
[X] A page can be viewed and edited in the Page Designer.
[X] To view the rendered version of the page, you run or submit it to the Oracle APEX engine.

2. Choose the two correct statements about PWA.

[X] Enables users to install the application on devices.
[X] Provides a customizable offline page when users are offline and cannot request the network.
[ ] To download the app as PWA, one must visit the App Store
[ ] An existing APEX app cannot be made a PWA.

3. Using the app builder component, you can perform which three tasks ?

[X] Edit pages in the page designer
[X] Install a sample app
[X] Create a new app
[ ] Run SQL scripts and commands

4. Choose the two statements that are TRUE about the Universal Theme in APEX.

[X] Easy customization.
[ ] The developer must have eensive knowledge about JavaScript, CSS, HTML in order to use the Universal Theme.
[ ] Not designed to work in tablets
[X] Responsible UI

5. Choose the three correct options in the given friendly URL syntax: https://example.com:5500/ords/r/mycompany/hr-app/update-employees?session=12345678901234

[X] hr is the application alias
[X] mycompany is the path-prefix which is by default the workspace name
[X] 12345678901234 is the session id. A new ID is generated for each session.
[ ] update employees is the PL/SQL procedure to update the employee details

### 4 Working with pages an regions

1. The Designer Toolbar allows you to perform which two of the following actions ?

[ ] Delete the application
[ ] Export the application
[X] Create a new page
[X] Navigate to Shared Components

2. When a button is pressed, an overlay window is positioned within the viewport. Which kind of pagemode is it ?

[ ] Help Page
[ ] Normal Page
[ ] Non-Modal Dialog
[X] Modal Dialog

3. Choose the three different ways in which you can add a checkbox to a page ?

[X] Right Click Body in the Rendering Tree and add a New Page item as Checkbox.
[X] Use the context sensitive menu in the Gallery pane.
[X] Drag and Drop the Checkbox item into the Layout pane.
[ ] Add a checkbox from the Property Editor.

4. Choose from the following the different kinds of page components you can create in APEX.

[ ] Interactive Grid
[ ] Smart Filters
[ ] Search Page
[ ] Faceted Search
[X] All of them

### 5 Developing Reports

1. Which type of pages behave similarly in functionality ?

[ ] Map
[X] Faceted Search
[ ] Cards
[X] Smart Filter

2. Which two of the following capablities are TRUE for both Interactive Reports and Interactive Grids ?

[X] End users can custimize how and what data is displayed.
[ ] End users can add, modify, and refresh data directly on the report
[X] End user can save the report
[ ] End user can rearange the report interactively using the mouse.

3. I want to hide a few columns in my interactive report. To do so, which option should I choose from action menu ?

[ ] Filter
[X] Columns
[ ] Format
[ ] Data

4. In a Classic Report, an end user can perform which one of the following actions ?

[X] Sort the columns of the report.
[ ] Rearrange the columns in the report.
[ ] Filter values of a column in the report.
[ ] Create Control Breaks in the report.

5. You can create a report in which of the three following methodes?

[ ] Create a report from Object Browser.
[X] Create a report when you create a new database application.
[X] Create a report as a new page in an application.
[X] Create a report region on a page in an application.

### 6 Managing and customizing interactive reports.

1. Which of the following types can end users save the customized Interactive Report as ?

[ ] Default Report
[ ] Cannot save report.
[X] A public report.
[X] A private report.

2. Choose the three aggregations you can apply on a column ?

[X] Average
[X] Count
[X] Sum
[ ] Standard Devations

3. Choose the two statements that are true about an Interactive Report. As a developer:

[ ] You cannot modify the report source query.
[X] You can customize the Actions menu to unclude or exclude certain options.
[X] You can customize the pagination.
[ ] You can modify the data in the report after running the app.

4. To highlight vertain rows in the interactive report based on a condition, you must :

[ ] Rows cannot be highlighted in an interactive report.
[ ] Edit the rows in the report and select a color.
[ ] Provide a conditional SQL query
[X] Choose a condition in Format > Highlight

5. Choose the two options provided in a column heading menu of an Interactive Report.

[ ] Delete
[X] Control Break
[X] Hide
[ ] Group By

### 7 Managing and customizing Interactive Grids

1. Which two are TRUE when the Edit option is NOT enabled for an Interactive Grid.

[X] The end user can customize the report.
[ ] The end user cannot create charts
[ ] The end user can edit underlying data in the database
[X] The end user cannot edit the unserlying data in the database.

2. Which of the the following statements are TRUW about saved Oublic Interactive Grids.

[X] To enable an end user to save interactive grid, the user must have the required permission
[ ] Any user may save public interactive reports
[X] Public Reports are available to all Users
[X] Only the users who creates the public interactive grid can save, rename, or delete it.

3. When a table or a SQL query returns many rows, an Interactive Grid is best displayed to the end user with pagination. The two types of pagination available are ?

[ ] No Pagination
[ ] Page and Scroll
[X] Page
[X] Scroll

4. Which two statements that are TRUE about charts in Interactive Grid.

[ ] Once the chart is created, it cannot be reconfigured.
[ ] You can create multible charts at a time in an interactive grid.
[X] Once a chart is created, you can switch the view between Grid and Chart view.
[X] To remove a chart, click Remove Chart icon (X) adjacent to the chart filter.

### 8 Create Application Page Controls

1. Let's say that there are two select lists on a page. Making a selection in the DEPARTMENT select list, determines which individuals displayed in the Employee list. This type of LOV is called :

[X] Cascading LOV
[ ] Static LOV
[ ] Dynamic LOV
[ ] Popup LOV

2. Choose from the below actions that can be performed when a button is clicked.

[ ] Redirect to a page in the same application.
[X] All of them
[ ] Submit a Page
[ ] Redirect to a page in a different application
[ ] Redirect to a URL

3. Choose the three types of page items that can be placed on a page.

[X] DatePicker
[X] Select List
[ ] Global variable
[X] Checkbox

4. What are the three types of List of Values (LOV) you can create on a page.

[X] Cascading LOV
[X] Static LOV
[X] Dynamic LOV
[ ] Popup LOV


### 9 Enhancing your application using Computations, Processes and Validations 

1. A page computation can be created from which of the two of the following tabs.

[X] Rendering Tree
[ ] Shared Components
[X] Processing
[ ] Dynamic Actions


2. Consider a customers report. A customer name is clicked in the report to display the customers detail form. When the items in the form dialog are updated and the user clicks Apply Changes, the page process is executed and the items from the page are used to update and commit the underlying table in the Oracle Database. What are the two types of events that occured in this scenario.

[ ] Page Validation
[X] Page Processing
[ ] Page Refresh
[X] Page Rendering

3. When you run an application, the APEX engine relies on which two processes.

[X] Show Page
[ ] Validate Page
[X] Accept Page
[ ] Run Page

4. When you click a Customer Name in the Customers report, the Customers Details form page is displayed. What are the events that occur in this scenario.

[ ] Page compilation
[ ] Page rendering and processing
[X] Page Rendering
[ ] Page Processing

### 10 Creating and using Dynamic Actions

1. An Employee form, the Commision and Hire Date fields are enabled only if the job is 'Salesman'. This can be achived by which feature of APEX ?

[ ] PL/SQL procedure
[X] Dynamic Actions
[ ] Processing
[ ] Conditional SQL

2. When you create a Dynamic Action, you specify the event that causes the dynamic action to fire. Choose the categories the events are classified to.

[X] All of them
[ ] Framework Events
[ ] Browser Events
[ ] Components Event
[ ] Custom Events

3. To create a Dynamic Action, you need to specify which three of the following options ?

[X] What action or actions are performed ?
[ ] What elements are affected by the action
[X] Why the action is performed
[X] When the action occurs

4. Which two statements are TRUE abot dynamic actions ?

[ ] It is not possible to Debug Dynamic Actions from the Developer Toolbar
[ ] Dynamic Actions require complex client side Javascript code.
[X] More dynamic actions you add to the page, the greater your overall page size
[X] Dynamic actions provide a way to define complex client-side behaviour declaratively without the need of JavaScript


### 11 Managing Cards, Faceted Search and Smart Filters

1. Select two features of a Smart Filters page.

[X] Consist of a single search field with filters at the top of the page and a report at the bottom.
[ ] Each filter represents the text entered by the user in the search field.
[ ] Consists of filters at the left side and report on the right side of the page.
[X] Each filter displayes as a suggestion chip with single count of how often the specific suggestion value occurs.

2. Select the three types of facets you can create in APEX.

[X] Range
[ ] Text Area
[X] Input Field
[X] Checkbox Group

3. Select the htree types of card layout you can create in APEX.

[ ] Vertical(Column)
[X] Horizontal(Row)
[X] Grid
[X] Float

4. Which of the three following statements are TRUE about Faceted Search ?

[X] The facets are displayed on the left and upper part of the acreen
[X] The right side of the page features a Search Result region, which can display as a classic report or a card layout.
[X] After the end user changes a facet, the reults, dependent facets, and occurrence counts refresh immediately.
[ ] You can create only 5 facets per page.

### 12 Creating and using Forms
