# Powershell Skeleton

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

Function getMetaData($objectName) {

$array = $objectName | get-member -MemberType Property | Select-Object Name, Definition
$array | Select-Object Name, Definition

}

$abc = get-process
$MetaData | getMetaData($abc)

```


#####
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
