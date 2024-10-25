# Powershell Skeleton

## wichtige Object Befehle


```
get-hotfix | where-object -Property Description -eq "Update" | sort-object -Property InstalledOn -Descending | Format-Table -AutoSize
get-hotfix | where-object -Property Description -eq "Update" | sort-object -Property InstalledOn -Descending | Format-Table -AutoSize -HideTableHeaders

get-process | select-object Id, Name, PriorityClass, HandleCount, TotalProcessorTime | Sort-Object -Property TotalProcessorTime -Descending | Format-Table -Autosize
get-process | select-object Id, Name, PriorityClass, HandleCount, TotalProcessorTime | Sort-Object -Property TotalProcessorTime -Descending | Format-Table -Autosize -HideTableHeaders

```

where-object -Property Name -eq String
sort-object -Property Name [-Descending]
