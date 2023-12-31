# Deletes files (hardcore mode - Windows only)

## pip install hcdel

### Recursive deletion: 

The function can recursively delete files and directories, ensuring that
 all nested files within a given path are removed.

### Dry run option (enabled by default!!): 

The dryrun argument allows users to preview the files that would be deleted without actually performing the deletion.
This can help verify the list of files before proceeding 
with the actual deletion.

### Print files option (enabled by default - can't be disabled when running with dryrun): 

The print_files argument enables users to see the files and directories being deleted. 
This can be useful for logging or providing feedback during the deletion process.

### pendmoves.exe to delete everything:

When dealing with stubborn files that cannot be deleted through normal means, 
PendMoves https://learn.microsoft.com/en-us/sysinternals/downloads/pendmoves helps in cleaning up such files effectively. 
It ensures that unwanted files are eventually removed (next reboot), 
preventing them from occupying unnecessary disk space 
or causing conflicts in the system.

### Integration and customization: 

The function can be easily integrated into existing scripts or applications. 
The arguments provide flexibility to customize the deletion process based
 on specific requirements. A compiled exe file is also available: https://github.com/hansalemaos/hcdel/raw/main/hcdel.exe



### In Python 

```python
# For security reasons, dryrun is always enabled, and always prints all files that would be deleted!
from hcdel.hcdel import delallfiles
delallfiles(
    path=r'C:\delfiles', dryrun = False, print_files = True
)

# Output 

Deleting: C:\delfiles\xff1fdx.mkv
Deleting: C:\delfiles\xfffdx.mkv
Deleting: C:\delfiles\xfffxxxxxxxdxxx  ddddddddd (2).mkv
Deleting: C:\delfiles\xfffxxxxxxxdxxx  ddddddddd.mkv
Deleting: C:\delfiles\xffxxxxaaxdx.mkv
The following files will be deleted the next reboot: # i kept this file open in my media player 
C:\delfiles\xfffxxxxxxxdxxx  ddddddddd.mkv

```

### CLI
```
# For security reasons, dryrun is always enabled, and always prints all files that would be deleted!
# https://github.com/hansalemaos/hcdel/raw/main/hcdel.exe

hcdel.exe --path "C:\delfiles" --dryrun 0 --print_files 1

```


# Arguments 

```python
delallfiles(
    path: str | None = None, dryrun: int | bool = 1, print_files: int | bool = 1
):
    r"""
    Recursively deletes files and directories.

    Args:
        path (str | None, optional): The path to the directory or file to be deleted. If None or '', the script exits with code 1. Defaults to None.
        dryrun (int | bool, optional): If set to 1 or True, performs a dry run and only prints the files that would be deleted without actually deleting them. If set to 0 or False, deletes the files and directories. Defaults to 1.
        print_files (int | bool, optional): If set to 1 or True, prints the files and directories being deleted. Defaults to 1.

    Returns:
        None

    Raises:
        None
```        
