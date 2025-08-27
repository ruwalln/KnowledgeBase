# Oracle SQLPLUS - Configuration and Scripting

## How to configure SQLPLUS using a systemwide and user specific profile

### SQLPLUS systemwide OR User specific Profile

Please locate the global Site profile in %ORACLE_HOME\SQLPLUS\ADMIN (Windows) OR $ORALE_HOME/SQLPLUS/ADMIN 
- Global Site SQLPLUS Profile : glogin.sql
- User specific SQLPLUS Profile : login.sql

### Environment variables OS and/or Windows registry 


<div class="tblformal" id="GUID-5A2953BF-9E2F-450B-AFBA-EE2846C59B5E__GUID-58035520-186F-435E-9D78-35D3E2BB6508">
                     <p class="titleintable">Table 2-1 <span class="italic"><span class="bold">Parameters or Environment Variables influencing SQL*Plus</span></span></p>
                     <table cellpadding="4" cellspacing="0" class="Formal" title="Parameters or Environment Variables influencing SQL*Plus" summary="Shows two columns of Parameters or Variables and descriptions that can influence SQL*Plus or iSQL*Plus" width="100%" frame="hsides" border="1" rules="rows">
                        <thead>
                           <tr align="left" valign="top">
                              <th align="left" valign="bottom" width="32%" id="d4739e84">Parameter or Variable</th>
                              <th align="left" valign="bottom" width="68%" id="d4739e87">Description</th>
                           </tr>
                        </thead>
                        <tbody>
                           <tr align="left" valign="top">
                              <td align="left" valign="top" width="32%" id="d4739e92" headers="d4739e84 ">
                                 <p>LD_LIBRARY_PATH<a id="d4739e95" class="indexterm-anchor"></a><a id="d4739e99" class="indexterm-anchor"></a></p>
                              </td>
                              <td align="left" valign="top" width="68%" headers="d4739e92 d4739e87 ">
                                 <p>Environment variable to specify the path used to search for libraries on UNIX and Linux. The environment variable may have a different name on some operating systems, such as DYLD_LIBRARY_PATH on Apple Mac OS, LIBPATH on IBM/AIX-5L, and SHLIB_PATH on HP-UX. Not applicable to Windows operating systems.</p>
                                 <p>Example</p><pre class="oac_no_warn" dir="ltr">$ORACLE_HOME/lib </pre></td>
                           </tr>
                           <tr align="left" valign="top">
                              <td align="left" valign="top" width="32%" id="d4739e111" headers="d4739e84 ">
                                 <p>LOCAL<a id="d4739e114" class="indexterm-anchor"></a><a id="d4739e118" class="indexterm-anchor"></a></p>
                              </td>
                              <td align="left" valign="top" width="68%" headers="d4739e111 d4739e87 ">
                                 <p>Windows environment variable to specify a connection string. Performs the same function as TWO_TASK on UNIX. </p>
                              </td>
                           </tr>
                           <tr align="left" valign="top">
                              <td align="left" valign="top" width="32%" id="d4739e126" headers="d4739e84 ">
                                 <p>NLS_LANG<a id="d4739e129" class="indexterm-anchor"></a><a id="d4739e133" class="indexterm-anchor"></a></p>
                              </td>
                              <td align="left" valign="top" width="68%" headers="d4739e126 d4739e87 ">
                                 <p>Environment variable to specify globalization behavior. </p>
                                 <p>Example</p><pre class="oac_no_warn" dir="ltr">american_america.utf8</pre></td>
                           </tr>
                           <tr align="left" valign="top">
                              <td align="left" valign="top" width="32%" id="d4739e145" headers="d4739e84 ">
                                 <p>ORACLE_HOME<a id="d4739e148" class="indexterm-anchor"></a><a id="d4739e152" class="indexterm-anchor"></a></p>
                              </td>
                              <td align="left" valign="top" width="68%" headers="d4739e145 d4739e87 ">
                                 <p>Environment variable to specify where SQL*Plus is installed. It is also used by SQL*Plus to specify where message files are located.</p>
                                 <p>Examples:</p><pre class="oac_no_warn" dir="ltr">d:\oracle\10g
/u01/app/oracle/product/v10g</pre></td>
                           </tr>
                           <tr align="left" valign="top">
                              <td align="left" valign="top" width="32%" id="d4739e164" headers="d4739e84 ">
                                 <p>ORA_EDITION<a id="d4739e167" class="indexterm-anchor"></a><a id="d4739e171" class="indexterm-anchor"></a></p>
                              </td>
                              <td align="left" valign="top" width="68%" headers="d4739e164 d4739e87 ">
                                 <p>Environment variable to specify the database edition to use. If you specify the edition with the CONNECT or SQLPLUS command option, <span class="italic">edition=</span><span class="italic">value</span>, it is used instead of ORA_EDITION. If no edition is specified in either the CONNECT or SQLPLUS command option, or in ORA_EDITION,  SQL*Plus connects to the default edition. 
                                 </p>
                                 <p>When ORA_EDITION is set, a subsequent STARTUP command in the session results in an ORA-38802 error.  To correct this, you must unset ORA_EDITION, then reconnect and shutdown the database, then start the database again. </p>
                              </td>
                           </tr>
                           <tr align="left" valign="top">
                              <td align="left" valign="top" width="32%" id="d4739e186" headers="d4739e84 ">
                                 <p>ORA_NLS10<a id="d4739e189" class="indexterm-anchor"></a><a id="d4739e193" class="indexterm-anchor"></a></p>
                              </td>
                              <td align="left" valign="top" width="68%" headers="d4739e186 d4739e87 ">
                                 <p>Environment variable to specify the locations of the NLS data and the user boot file in SQL*Plus 10.2. The default location is $ORACLE_HOME/nls/data. In a system with both Oracle9<span class="italic">i</span> and 10<span class="italic">g</span>, or a system under version upgrade, you should set ORA_NLS10 for Oracle 10<span class="italic">g</span> and set ORA_NLS33 for 9<span class="italic">i</span>. The default NLS location in 9<span class="italic">i</span> was $ORACLE_HOME/common/nls/admin/data.
                                 </p>
                              </td>
                           </tr>
                           <tr align="left" valign="top">
                              <td align="left" valign="top" width="32%" id="d4739e216" headers="d4739e84 ">
                                 <p>ORACLE_PATH<a id="d4739e219" class="indexterm-anchor"></a><a id="d4739e223" class="indexterm-anchor"></a></p>
                              </td>
                              <td align="left" valign="top" width="68%" headers="d4739e216 d4739e87 ">
                                 <p>Environment variable to specify the location of SQL scripts. If SQL*Plus cannot find the file in ORACLE_PATH, or if ORACLE_PATH is not set, it searches for the file in the current working directory. </p>
                                 <p>Not applicable to Windows</p>
                              </td>
                           </tr>
                           <tr align="left" valign="top">
                              <td align="left" valign="top" width="32%" id="d4739e233" headers="d4739e84 ">
                                 <p>ORACLE_SID<a id="d4739e236" class="indexterm-anchor"></a><a id="d4739e240" class="indexterm-anchor"></a></p>
                              </td>
                              <td align="left" valign="top" width="68%" headers="d4739e233 d4739e87 ">
                                 <p>Environment variable to specify the database instance, optional</p>
                              </td>
                           </tr>
                           <tr align="left" valign="top">
                              <td align="left" valign="top" width="32%" id="d4739e248" headers="d4739e84 ">
                                 <p>PATH<a id="d4739e251" class="indexterm-anchor"></a><a id="d4739e255" class="indexterm-anchor"></a></p>
                              </td>
                              <td align="left" valign="top" width="68%" headers="d4739e248 d4739e87 ">
                                 <p>Environment variable to specify the path to search for executables, and DLLs in Windows. Typically includes ORACLE_HOME/bin</p>
                              </td>
                           </tr>
                           <tr align="left" valign="top">
                              <td align="left" valign="top" width="32%" id="d4739e263" headers="d4739e84 ">
                                 <p>SQLPATH<a id="d4739e266" class="indexterm-anchor"></a><a id="d4739e270" class="indexterm-anchor"></a><a id="d4739e274" class="indexterm-anchor"></a><a id="d4739e278" class="indexterm-anchor"></a></p>
                              </td>
                              <td align="left" valign="top" width="68%" headers="d4739e263 d4739e87 ">
                                 <p>Environment variable or Windows registry entry to specify the location of SQL
                                scripts. SQL*Plus searches for SQL scripts, including
                                    <span class="italic">login.sql</span>, in the directories specified by SQLPATH.
                                SQLPATH is a colon-separated list of directories. There is no
                                default value set in UNIX installations.
                                 </p>
                                 <p>In Windows, SQLPATH is defined in a registry entry during installation. For more information about the SQLPATH registry entry, see <a href="configuring-SQL-Plus.html#GUID-A91DD984-84ED-4D67-9983-938FCFC3665E">SQLPATH Registry Entry</a>.
                                 </p>
                              </td>
                           </tr>
                           <tr align="left" valign="top">
                              <td align="left" valign="top" width="32%" id="d4739e295" headers="d4739e84 ">
                                 <p>TNS_ADMIN<a id="d4739e298" class="indexterm-anchor"></a><a id="d4739e302" class="indexterm-anchor"></a></p>
                              </td>
                              <td align="left" valign="top" width="68%" headers="d4739e295 d4739e87 ">
                                 <p>Environment variable to specify the location of the tnsnames.ora file. If not specified, $ORACLE_HOME/network/admin is used </p>
                                 <p>Example</p><pre class="oac_no_warn" dir="ltr">h:\network 
/var/opt/oracle</pre></td>
                           </tr>
                           <tr align="left" valign="top">
                              <td align="left" valign="top" width="32%" id="d4739e315" headers="d4739e84 ">
                                 <p>TWO_TASK<a id="d4739e318" class="indexterm-anchor"></a><a id="d4739e322" class="indexterm-anchor"></a></p>
                              </td>
                              <td align="left" valign="top" width="68%" headers="d4739e315 d4739e87 ">
                                 <p>UNIX environment variable to specify a connection string. Connections that do not specify a database will connect to the database specified in TWO_TASK.</p>
                                 <p>Example</p><pre class="oac_no_warn" dir="ltr">TWO_TASK=MYDB
export TWO_TASK
sqlplus hr</pre><p>is the same as:</p><pre class="oac_no_warn" dir="ltr">sqlplus hr@MYDB</pre></td>
                           </tr>
                        </tbody>
                     </table>
                  </div>

### Install and configure SQLPLUS Help System in Oracle Database

- Scripts to use are located in $ORACLE_HOME/SQLPLUS/ADMIN/HELP

```
-- first login as system user to install SQLPLUS Help in the database

conn system/manager

-- for LINUX and UNIX use this
@$ORACLE_HOME/sqlplus/admin/help/hlpbld.sql helpus.sql

-- for Windows use this
@%ORACLE_HOME%\SQLPLUS\ADMIN\HELP\HLPBLD.SQL HELPUS.SQL

```
### Using Help inside SQLPLUS command line interface

- Enter Help to get help for SQLPLUS from the SQL> Prompt.

```
SYSTEM@XE SQL> help

 HELP
 ----

 Accesses this command line help system. Enter HELP INDEX or ? INDEX
 for a list of topics.

 You can view SQL*Plus resources at
     http://www.oracle.com/technology/documentation/

 ******************************************************************************

 HELP|? [topic]
```
- Enter HELP INDEX to get an overview for all available Help topics.

```
SYSTEM@XE SQL> help index

Enter Help [topic] for help.

 @             COPY         PASSWORD                 SHOW
 @@            DEFINE       PAUSE                    SHUTDOWN
 /             DEL          PRINT                    SPOOL
 ACCEPT        DESCRIBE     PROMPT                   SQLPLUS
 APPEND        DISCONNECT   QUIT                     START
 ARCHIVE LOG   EDIT         RECOVER                  STARTUP
 ATTRIBUTE     EXECUTE      REMARK                   STORE
 BREAK         EXIT         REPFOOTER                TIMING
 BTITLE        GET          REPHEADER                TTITLE
 CHANGE        HELP         RESERVED WORDS (SQL)     UNDEFINE
 CLEAR         HISTORY      RESERVED WORDS (PL/SQL)  VARIABLE
 COLUMN        HOST         RUN                      WHENEVER OSERROR
 COMPUTE       INPUT        SAVE                     WHENEVER SQLERROR
 CONNECT       LIST         SET                      XQUERY
```

### SQLPLUS Command Overview


| COMMAND |  Description |
| ---------------- | --------------------- |
| **@**   | Runs the SQL*Plus statements in the specified script. The script can be called from the local file system or from a web server. The @ command functions similarly to @@ and START. |
| **@@**    |  Runs a script. This command is almost identical to the @ (at sign) command. When running nested scripts it looks for nested scripts in the same path or url as the calling script. The @@ command functions similarly to @ and START. |   
| **/**       | Executes the most recently executed SQL command or PL/SQL block which is stored in the SQL buffer. |   
| **ACCEPT**    |  Reads a line of input and stores it in a given substitution variable. |
| **APPEND**     | Adds specified text to the end of the current line in the SQL buffer. To separate text from the preceding characters with a space, enter two spaces between APPEND and text. To APPEND text that ends with a semicolon, end the command with two semicolons (SQL*Plus interprets a single semicolon as an optional command terminator). |
| **ARCHIVE LOG LIST** | Displays information about redo log files. |
| **ATTRIBUTE**  | Specifies display characteristics for a given attribute of an Object Type column, such as the format of NUMBER data. Columns and attributes should not have the same names as they share a common namespace. Lists the current display characteristics for a single attribute or all attributes. |
| **BREAK**      |  Specifies where changes occur in a report and the formatting action to perform, such as: - suppressing display of duplicate values for a given column - skipping a line each time a given column value changes- printing computed figures each time a given column value changes or at the end of the report. Enter BREAK with no clauses to list the current BREAK definition. |
| **BTITLE**     |  Places and formats a specified title at the bottom of each report page, or lists the current BTITLE definition. |
| **CHANGE**     |  Changes the first occurrence of the specified text on the current line of the SQL buffer. The buffer has no command history list and does not record SQL*Plus commands. |
| **CLEAR**      | Resets or erases the current value or setting for the specified option. [CLEAR SCREEN] |
| **COLUMN**     |  Specifies display attributes for a given column, such as: - text for the column heading - alignment for the column heading - format for NUMBER data - wrapping of column data Also lists the current display attributes for a single column or all columns. |
| **COMPUTE**    | In combination with the BREAK command, calculates and prints summary lines using various standard computations. Also lists all COMPUTE definitions. |
| **CONNECT**    | Connects a given username to the Oracle Database. When you run a CONNECT command, the site profile, glogin.sql, and the user profile, login.sql, are processed in that order. CONNECT does not repromptfor username or password if the initial connection does not succeed. |
| **COPY**       | Copies data from a query to a table in the same or another database. COPY supports CHAR, DATE, LONG, NUMBER and VARCHAR2. |
| **DEFINE**       | Specifies a substitution variable and assigns a CHAR value to it, or lists the value and variable type of a single variable or all variables. |
| **DEL**          | Deletes one or more lines of the SQL buffer. The buffer has no command history list and does not record SQL*Plus commands. |
| **DESCRIBE**     | Lists the column definitions for a table, view, or synonym, or the specifications for a function or procedure. |
| **DISCONNECT**   | Commits pending changes to the database and logs the current user out of Oracle, but does not exit SQL*Plus. In SQL*Plus command line, use EXIT or QUIT to log out of Oracle and return control to your computer's operating system. |
| **EDIT**         | Invokes an operating system text editor on the contents of the specified file or on the contents of the SQL buffer. The buffer has no command history list and does not record SQL*Plus commands. |
| **EXECUTE**      | Executes a single PL/SQL statement or runs a stored procedure. |
| **EXIT**         | Commits or rolls back all pending changes, logs out of Oracle, terminates SQL*Plus and returns control to the operating system. |
| **GET**          | Loads a SQL statement or PL/SQL block from a script into the SQL buffer. The buffer has no command history list and does not record SQL*Plus commands. |
| **HELP**         | Accesses this command line help system. Enter HELP INDEX or ? INDEX for a list of topics. |
| **HISTORY**      | Stores, lists, executes, or edits commands entered during the current SQL*Plus session. |
| **HOST**         | Executes an operating system command without leaving SQL*Plus. Enter HOST without command to display an operating system prompt. You can then enter multiple operating system commands. |
| **INPUT**        |  Adds one or more new lines of text after the current line in the SQL buffer. The buffer has no command history list and does not record SQL*Plus commands. |
| **LIST**         | Lists one or more lines of the most recently executed SQL command or PL/SQL block which is stored in the SQL buffer. Enter LIST with no clauses to list all lines. In SQLPlus command-line you can also use ";" to list all the lines in the SQL buffer. The buffer has no command history list and does not record SQLPlus commands. |
| **PASSWORD**      |  Allows you to change a password without displaying it on an input device. |        
| **PAUSE**           | Displays the specified text then waits for the user to press RETURN. |       
| **PRINT**             | Displays the current values of bind variables, or lists all bind variables. |
| **PROMPT**              | Sends the specified message or a blank line to the user's screen. |  
| **QUIT**                  |  Commits or rolls back all pending changes, logs out of Oracle, terminates SQL*Plus and returns control to the operating system. |
| **RECOVER**                | Performs media recovery on one or more tablespaces, one or more datafiles, or the entire database. |
| **REMARK**                 | Begins a comment in a script. SQL*Plus does not interpret the comment as a command.|
| **REPFOOTER**              | Places and formats a footer at the bottom of a report, or lists the REPFOOTER definition. |
| **REPHEADER**              | Places and formats a header at the top of a report, or lists the REPHEADER definition. |
| **RESERVED WORDS (SQL)**   | (see list xx.xx)
| **RESERVED WORDS (PL/SQL)**| (see list xx.xx)
| **RUN**                    | 
| **SAVE**                   | 
| **SET**| 
| **SHOW** | 
| **SHUTDOWN** | 
| **SPOOL** | 
| **SQLPLUS** | 
| **START** | 
| **STARTUP** | 
| **STORE** | 
| **TIMING** | 
| **TTITLE** | 
| **UNDEFINE** | 
| **VARIABLE** | 
| **WHENEVER OSERROR** | 
| **WHENEVER SQLERROR** | 
| **XQUERY** | 

### Oracle Reserved Words PL/SQL

PL/SQL Reserved Words have special meaning in PL/SQL, and may not be used
 for identifier names (unless enclosed in "quotes").

 An asterisk (*) indicates words are also SQL Reserved Words.
|         1      |     2           |    3           |    4            |    5       |
| ------------- | -------------- | ------------- | -------------- | --------- |
| ALL*          |  DESC*         |  JAVA         |   PACKAGE      |   SUBTYPE |
| ALTER*        |  DISTINCT*     |  LEVEL*       |  PARTITION     |  SUCCESSFUL* |
|  AND*        |    DO           |   LIKE*       |    PCTFREE*    |    SUM |
|  ANY*        |    DROP*        |   LIMITED     |    PLS_INTEGER |    SYNONYM* |
|  ARRAY       |    ELSE*        |   LOCK*       |    POSITIVE    |    SYSDATE* |
|  AS*         |   ELSIF         |  LONG*        |   POSITIVEN    |   TABLE* |
|  ASC*        |    END          |   LOOP        |    PRAGMA      |    THEN* |
|  AT          |    EXCEPTION    |   MAX         |    PRIOR*      |    TIME |
|  AUTHID      |    EXCLUSIVE*   |   MIN         |    PRIVATE     |    TIMESTAMP |
|  AVG          |   EXECUTE      |   MINUS*      |    PROCEDURE   |    TIMEZONE_ABBR |
|  BEGIN        |   EXISTS*      |   MINUTE      |    PUBLIC*     |    TIMEZONE_HOUR |
|  BETWEEN*     |   EXIT         |   MLSLABEL*   |   RAISE        |   TIMEZONE_MINUTE |
|  BINARY_INTEGER | EXTENDS      |   MOD         |    RANGE       |    TIMEZONE_REGION |
|  BODY          |  EXTRACT      |   MODE*       |    RAW*        |    TO* |
|  BOOLEAN       |  FALSE        |   MONTH       |    REAL        |    TRIGGER* |
|  BULK          |  FETCH        |   NATURAL     |    RECORD      |    TRUE |
|  BY*           |  FLOAT*       |   NATURALN    |    REF         |    TYPE |
|  CHAR*         |  FOR*         |   NEW         |    RELEASE     |    UI |
|  CHAR_BASE     |  FORALL       |   NEXTVAL     |    RETURN      |    UNION* |
|  CHECK*        |  FROM*        |   NOCOPY      |    REVERSE     |    UNIQUE* |
|  CLOSE         |  FUNCTION     |   NOT*        |    ROLLBACK    |    UPDATE* |
|  CLUSTER*      |  GOTO         |   NOWAIT*     |    ROW*        |    USE |
|  COALESCE      |  GROUP*       |   NULL*       |    ROWID*      |    USER* |
|  COLLECT       |  HAVING*      |   NULLIF      |    ROWNUM*     |    VALIDATE* |
|  COMMENT*      |  HEAP         |   NUMBER*     |    ROWTYPE     |    VALUES* |
|  COMMIT        |  HOUR         |   NUMBER_BASE |    SAVEPOINT   |    VARCHAR* |
|  COMPRESS*     |  IF           |   OCIROWID    |    SECOND      |    VARCHAR2* |
|  CONNECT*      |  IMMEDIATE*   |   OF*         |    SELECT*     |    VARIANCE |
|  CONSTANT      |  IN*          |   ON*         |    SEPERATE    |    VIEW* |
|  CREATE*       |  INDEX*       |   OPAQUE      |    SET*        |    WHEN |
|  CURRENT*      |  INDICATOR    |   OPEN        |    SHARE*      |    WHENEVER* |
|  CURRVAL       |  INSERT*      |   OPERATOR    |    SMALLINT*   |    WHERE*  |
|  CURSOR        |  INTEGER*     |   OPTION*     |    SPACE       |    WHILE |
|  DATE*         |  INTERFACE    |   OR*         |    SQL         |    WITH* |
|  DAY           |  INTERSECT*   |   ORDER*      |    SQLCODE     |    WORK |
|  DECIMAL*      |  INTERVAL     |   ORGANIZATION|    SQLERRM     |    WRITE |
|  DECLARE       |  INTO*        |   OTHERS      |    START*      |    YEAR |
|  DEFAULT*      |  IS*          |   OUT         |    STDDEV      |    ZONE |

## HowTo Import a CSV File into a Database Table using SQLCl

- First run SQLCl client and connect to a valid database.
- Afterwards check the current loadformat using the following command SHOW LOADFORMAT
- change the settings using SET LOADFORMAT <param>

```
set loadformat csv
show loadformat
SQL> show loadformat

csv
column_names on
delimiter ,
enclosures ""
double off
encoding UTF8
row_limit off
row_terminator default
skip_rows 0
skip_after_names
```

- To change the delimiter in loadformat use the following command
```
set loadformat delimited delimiter ;;
SQL> show loadformat

csv
column_names on
delimiter ;
enclosures ""
double off
encoding UTF8
row_limit off
row_terminator default
skip_rows 0
skip_after_names
```

- Loading a CSV File Format into a non existing table using the CREATE clause
```
load MYDATA C:\users\zbook\app\oracle\tools\sqlcl-24.2.0.180.1721\sqlcl\bin\mydata.csv CREATE
```

- Loading CSV Data into the created table MYDATA
```
load MYDATA C:\users\zbook\app\oracle\tools\sqlcl-24.2.0.180.1721\sqlcl\bin\mydata.csv
```
## HowTo import a CSV Fileformat into ORACLE using a Powershell Script

- This Script imports a CSV Fileformat into a Oracle Database and modifies a table MYDATA by add a primary key using SQLCL Tools (SQL Developer Command Line)
```
# --------------------------------------------------
# --> start-process using sqlplus using powershell
# --------------------------------------------------

$db="FREEPDB1"
$dbuser="ruwalln"
$dbpass=""

#
# SQL Query - Construction here
#

$sqlcmd = '
set loadformat csv
set loadformat delimited delimiter ;;
load MYDATA C:\users\zbook\app\oracle\tools\sqlcl-24.2.0.180.1721\sqlcl\bin\mydata.csv CREATE
load MYDATA C:\users\zbook\app\oracle\tools\sqlcl-24.2.0.180.1721\sqlcl\bin\mydata.csv
alter table MYDATA
add constraint mydata_pk primary key (ID);
info mydata'

#
# ORACLE Database Connection here
#

$dbConnect = get-credential -UserName $dbuser -Message "Bitte ORACLE User/Passw@$db angeben :" 

$dbpass=$dbConnect.GetNetworkCredential().Password
$dbuser=$dbconnect.GetNetworkCredential().UserName

#start-process "$sqlcmd | sqlplus $dbuser/$dbpass@$db" -WindowStyle Normal -Wait 

#
# SQL*Plus execution here
#

$sqlOutput = $sqlcmd | .\sql -S $dbuser/$dbpass@$db

foreach($line in $sqlOutput) {
	if($line -match $regex) {
		
	   write-host $line
	}
}	

#-split $sqlOutput
```

## HowTo import a CSV Fileformat into ORACLE using a LINUX Shell Script

```
#!/bin/bash

db="FREEPDB1"
dbuser="system"
dbpass="manager"

SQLCMD="
set loadformat csv
load MYPROCESS /home/oracle/process.csv CREATE
load MYPROCESS /home/oracle/process.csv
alter table MYPROCESS
add constraint myprocess_pk primary key (pid);
"

echo "$SQLCMD" | /home/oracle/sqlcl/bin/sql -S $dbuser/$dbpass@$db

```
