# deleteAll_node_modules
delete node_modules from all subdirectories of current dir
```bash
# Find all "node_modules" folders
Get-ChildItem -Path . -Recurse -Directory -Filter "node_modules" | Where-Object { $_.FullName -notmatch '\\node_modules\\' } | Select-Object -ExpandProperty FullName

# Delete all "node_modules" folders
Get-ChildItem -Path . -Recurse -Directory -Filter "node_modules" | Remove-Item -Recurse -Force

# Verify deletion
Get-ChildItem -Path . -Recurse -Directory -Filter "node_modules" | Where-Object { $_.FullName -notmatch '\\node_modules\\' } | Select-Object -ExpandProperty FullNameThis should return an empty list, indicating that all "node_modules" folders have been deleted.
```

[reference](https://medium.com/@aungmo/free-up-disk-space-a-step-by-step-guide-to-removing-node-modules-folders-in-powershell-fedb3de73eed)
