# Powershell Skeleton

## wichtige Object Befehle


```


get-hotfix | where-object -Property Description -eq "Update" | sort-object -Property InstalledOn -Descending | Format-Table -AutoSize
get-hotfix | where-object -Property Description -eq "Update" | sort-object -Property InstalledOn -Descending | Format-Table -AutoSize -HideTableHeaders

get-process | select-object Id, Name, PriorityClass, HandleCount, TotalProcessorTime | Sort-Object -Property TotalProcessorTime -Descending | Format-Table -Autosize
get-process | select-object Id, Name, PriorityClass, HandleCount, TotalProcessorTime | Sort-Object -Property TotalProcessorTime -Descending | Format-Table -Autosize -HideTableHeaders
get-process | select-object Id, Name, PriorityClass, Handle, HandleCount, TotalProcessorTime, Threads | Sort-Object -Property TotalProcessorTime -Descending | Format-Table -Autosize

```

where-object -Property Name -eq String
select-object ObjectName 
sort-object -Property Name [-Descending]
Format-Table -AutoSize -HideTableHeaders

