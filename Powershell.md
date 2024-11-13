# Powershell Skeleton Knowledge

## Voreinstellungen von Powershell Command Console

- Execute and running the Default Powershell Command Window using Powershell.exe
- Check where the Default User Profile for the Powershell Command Console is stored using [$profile]
- if not exists you are able to create it using [New-item –type file –force $profile]
- to see your Default Powershell Options in the Powershell Command Shell Window use [Get-PSReadlineOption]
    https://learn.microsoft.com/de-de/powershell/module/PSReadline/Set-PSReadlineOption?view=powershell-5.1
- Display all available Colors in Powershell

```
$colors = [enum]::GetValues([System.ConsoleColor])
Foreach ($bgcolor in $colors){
Foreach ($fgcolor in $colors) { Write-Host "$fgcolor|" -ForegroundColor $fgcolor -BackgroundColor $bgcolor -NoNewLine }
Write-Host " on $bgcolor"
}

```
  
<a href="https://learn.microsoft.com/de-de/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-7.4" target="_blank">Informationen zu Profilen</a>
```
# check where the Default Powershell User Profile is stored

PS C:\Users\zbook> $profile
C:\Users\zbook\OneDrive\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1
```

<a href="https://learn.microsoft.com/de-de/powershell/module/microsoft.powershell.management/new-item?view=powershell-5.1" target="_blank">$Profile</a>
```
# If not exists create one to make changes afterwards

PS C:\Users\zbook\OneDrive\Documents\WindowsPowerShell> New-item -type file -force $profile

    Verzeichnis: C:\Users\zbook\OneDrive\Documents\WindowsPowerShell

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        13.11.2024     10:17              0 Microsoft.PowerShell_profile.ps1
```

<a href="https://learn.microsoft.com/de-de/powershell/module/psreadline/get-psreadlineoption?view=powershell-5.1)" target="_blank">Get-PSReadlineOption</a>
```
# Check the current settings of the Default Powershell User Profile

PS C:\Users\zbook\OneDrive\Documents\WindowsPowerShell> Get-PSReadlineOption


EditMode                               : Windows
AddToHistoryHandler                    :
HistoryNoDuplicates                    : True
HistorySavePath                        : C:\Users\zbook\AppData\Roaming\Microsoft\Windows\PowerShell\PSReadLine\ConsoleHost_history.txt
HistorySaveStyle                       : SaveIncrementally
HistorySearchCaseSensitive             : False
HistorySearchCursorMovesToEnd          : False
MaximumHistoryCount                    : 4096
ContinuationPrompt                     : >>
ExtraPromptLineCount                   : 0
PromptText                             : >
BellStyle                              : Audible
DingDuration                           : 50
DingTone                               : 1221
CommandsToValidateScriptBlockArguments : {ForEach-Object, %, Invoke-Command, icm...}
CommandValidationHandler               :
CompletionQueryItems                   : 100
MaximumKillRingCount                   : 10
ShowToolTips                           : True
ViModeIndicator                        : None
WordDelimiters                         : ;:,.[]{}()/\|^&*-=+'"–—―
CommandColor                           : "$([char]0x1b)[93m"
CommentColor                           : "$([char]0x1b)[32m"
ContinuationPromptColor                : "$([char]0x1b)[33m"
DefaultTokenColor                      : "$([char]0x1b)[33m"
EmphasisColor                          : "$([char]0x1b)[96m"
ErrorColor                             : "$([char]0x1b)[91m"
KeywordColor                           : "$([char]0x1b)[92m"
MemberColor                            : "$([char]0x1b)[97m"
NumberColor                            : "$([char]0x1b)[97m"
OperatorColor                          : "$([char]0x1b)[90m"
ParameterColor                         : "$([char]0x1b)[90m"
SelectionColor                         : "$([char]0x1b)[35;43m"
StringColor                            : "$([char]0x1b)[36m"
TypeColor                              : "$([char]0x1b)[37m"
VariableColor                          : "$([char]0x1b)[92m"

```

To modify the current Settings of stored settings in the $Profile var you are able to set new values to a hashtable called $PSReadLineOptions

For Reference look inside the wiki to get the corrent ANSI Esc Characters to modify -Colors

<a href="https://en.wikipedia.org/wiki/ANSI_escape_code#SGR_parameters">ANSI Escape Sequences</a>
<p></p>
<a href="https://jafrog.com/2013/11/23/colors-in-terminal.html">Colors in Terminal</a>

```
# set multible colors using one command

Set-PSReadLineOption -Colors @{
  Command            = 'Magenta'
  Number             = 'DarkGray'
  Member             = 'DarkGray'
  Operator           = 'DarkGray'
  Type               = 'DarkGray'
  Variable           = 'DarkGreen'
  Parameter          = 'DarkGreen'
  ContinuationPrompt = 'DarkGray'
  Default            = 'DarkGray'
}

# OR using a hashtable variable to modify the settings

$PSReadLineOptions = @{ Colors = @{ 
    "Command"="Green"
    }}

```

TODO CONTINUE !!!


## wichtige Object Befehle


```

get-hotfix | where-object -Property Description -eq "Update" | sort-object -Property InstalledOn -Descending | Format-Table -AutoSize
get-hotfix | where-object -Property Description -eq "Update" | sort-object -Property InstalledOn -Descending | Format-Table -AutoSize -HideTableHeaders

get-process | select-object Id, Name, PriorityClass, HandleCount, TotalProcessorTime | Sort-Object -Property TotalProcessorTime -Descending | Format-Table -Autosize
get-process | select-object Id, Name, PriorityClass, HandleCount, TotalProcessorTime | Sort-Object -Property TotalProcessorTime -Descending | Format-Table -Autosize -HideTableHeaders
get-process | select-object Id, Name, PriorityClass, Handle, HandleCount, TotalProcessorTime, Threads | Sort-Object -Property TotalProcessorTime -Descending | Format-Table -Autosize

```
##### Metadata Function um TableHeaders auszulesen


```
# --------------------------------------------
# --> ConsoleInput1.ps
# --------------------------------------------
# Verwendung von Functions in der Powershell
# mit Parameter Wert Uebergabe 
# --------------------------------------------

Function getMetaData {
    param(
        [Parameter(Mandatory,Position=0)]
        [Object] $objectName
    )
    $array = $objectName | get-member -MemberType Property | Select-Object Name, Definition | Format-Table -AutoSize
    # hier erfolgt die Ausgabe
    $array
}

# --> Steuer Variablen fuer User Input und Endlosschleife

$endless=$true
$userInput=0

# --> wiederhole bis UserInput = 99

While($endless) {
    write-host "Bitte Funktion auswaehlen"
    write-host "-----------------------------------"
    write-host "(1) get-disk Table Definition"
    write-host "(2) get-process Table Definition"
    write-Host "-----------------------------------"
    $userInput = read-Host "UserInput 1,2,99 for EXIT"
    switch($userInput) {
     '1' 
      { 
        $abc = get-disk
        $getTable = getMetaData -objectName $abc 
        $getTable    
      }
     '2' 
      {
        $abc = get-process
        $getTable = getMetaData -objectName $abc
        $getTable          
      }
    '99' 
      {
        $endless=$false
      }
   }
}                           

```

##### Object Befehle zum filtern, Spalten selektieren, Sortieren von Spalten, automatsiches Darstellen von Tabellen

- where-object -Property Name -eq String
- select-object ObjectName 
- sort-object -Property Name [-Descending]
- Format-Table -AutoSize -HideTableHeaders

```
PS C:\WINDOWS\system32> get-history

  Id CommandLine
  -- -----------
   1 Get-Counter -Counter "\Processor(_Total)\% Processor Time" -SampleInterval 2 -MaxSamples 3
   2 get-counter
   3 get-counter -ListSet
   4 get-counter -ListSet *
   5 get-computerinfo
   6 get-computerinfo | select-object OSHotfixes
   7 get-computerinfo | select-object OSHotfixes
   8 get-hotfix
   9 $hotfixes = get-computerinfo | select-object OSHotfixes
  10 $hotfixes
  11 array.$hotfixes(1)
  12 get-clipboard
  13 $hotfixes = get-computerinfo | select-object OSHotfixes | sort-object -Property InstalledOn
  14 $hotfixes
  15 get-hotfixes |sort-object -Property InstalledOn
  16 get-hotfixe |sort-object -Property InstalledOn
  17 get-hotfix |sort-object -Property InstalledOn
  18 get-hotfix |sort-object -Property InstalledOn -Descending
  19 get-hotfix |sort-object -Property InstalledOn -Ascending
  20 get-hotfix |sort-object -Property InstalledOn -Descending
  21 get-hotfix |where-object -Property Description -eq "Update" | sort-object -Property InstalledOn -Descending
  22 get-hotfix | where-object -Property Description -eq "Update" | sort-object -Property InstalledOn -Descending
  23 get-hotfix | where-object -Property Description -eq "Update" | format-table -HideTableHeaders | sort-object -Property InstalledOn -Descending
  24 get-hotfix | where-object -Property Description -eq "Update" | sort-object -Property InstalledOn -Descending | Format-Table -HideTableHeaders
  25 get-hotfix | where-object -Property Description -eq "Update" | sort-object -Property InstalledOn -Descending | Format-Table -HideTableHeaders -AutoSize
  26 get-hotfix | where-object -Property Description -eq "Update" | sort-object -Property InstalledOn -Descending | Format-Table -AutoSize
  27 get-hotfix | where-object -Property Description -eq "Update" | sort-object -Property InstalledOn -Descending | Format-Table -AutoSize
  28 get-process | where-object -Property Description -eq "Update" | sort-object -Property InstalledOn -Descending | Format-Table -AutoSize
  29 get-process
  30 get-process
  31 get-process | sort-object -Property "CPU(s)" -Descending
  32 get-process | select-object * | Format-Table -Autosize
  33 get-process | select-object Id, Name, PriorityClass, HandleCount, ProcessorTime | Sort-Object -Property TotalProcessorTime -Descending | Format-Table -Autosize
  34 get-process | select-object Id, Name, PriorityClass, HandleCount, ProcessorTime  | Format-Table -Autosize
  35 get-process | select-object Id, Name, PriorityClass, HandleCount, TotalProcessorTime  | Format-Table -Autosize
  36 get-process | select-object Id, Name, PriorityClass, HandleCount, TotalProcessorTime | Sort-Object -Property TotalProcessorTime -Descending | Format-Table -Autosize
  37 get-process | select-object Id, Name, PriorityClass, Handle, HandleCount, TotalProcessorTime | Sort-Object -Property TotalProcessorTime -Descending | Format-Table -Autosize
  38 get-process | select-object Id, Name, PriorityClass, Handle, HandleCount, TotalProcessorTime, Threads | Sort-Object -Property TotalProcessorTime -Descending | Format-Table -Autosize
  39 get-process | select-object Id, Name, PriorityClass, Handle, HandleCount, TotalProcessorTime, Threads | Sort-Object -Property TotalProcessorTime -Descending | Format-Table -Autosize
```
