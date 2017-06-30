# collect.py
Rename or Copy specified files or directories

Synopsis:
    
    Rename files or folders using a pattern containing an index as in 'image0001.png'.
    This number in the file name will be incremented automatically for each file,
    and no existing file will not overwritten, such that this can be used to pool
    together many similar files in a common directory.
    
Syntax:
    
    collect.py PATTERN [INTEGER] [--copy] PATHS

Arguments:
    
    PATTERN is a string containing '%i' or '%0Xi', for example 'image%04i.png'
    if specified, --copy will copy the files/directory instead of moving them
    if specified, INTEGER is the first index to be used (default=0)
    PATHS is a list of file or directories

Examples:
    
    collect.py image%04i.png  *.png
       will rename image files to: image0000.png, image0001.png, etc.
    
    collect.py --copy image%04i.png 1 run*/image.png"
       will copy the image files, starting at index 1
    
F. Nedelec, 2012--2017.
