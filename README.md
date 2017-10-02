# collect.py
Rename or copy specified files or directories

###Synopsis:
    
    Rename files or folders following a pattern containing an integer index,
    as in 'image0001.png'. The file will be moved in the current directory
    
    The number in the file name is incremented automatically for each file, and
    also if files with this name already exist. Thus pre-existing files are not 
    overwritten, such that 'collect.py' can be used to pool together many similar
    files in a common directory.
    
###Syntax:
    
    collect.py PATTERN [INTEGER] [--copy] PATH1 [PATH2] [PATH3] ...

###Arguments:
    
    PATTERN specifies the name of the output files, and should contain a variable
    part that will be replaced by an integer. It can be a 'scanf' compatible 
    pattern such as '%i' or '%0Xi', for example 'image%04i.png'.
    A character '%' repeated multiple times, such as `%%%%` or `%%%%%%`, can be 
    used to directly specify the size of the integer portion of the name.
    
    The pattern can include a directory, and if this directory does not exist,
    collect.py will attemtps to create it before moving the file.

    if specified, --copy will copy the files/directory instead of moving them
    
    if specified, INTEGER is the first index to be used (default=0)

    PATH1, PATH2, etc. is a list of files or directories

###Examples:
    
    collect.py image%%%%.png  *.png
       will rename image files to: image0000.png, image0001.png, etc.
    
    collect.py --copy image%%%%.png 1 run*/image.png
       will copy the image files, starting at index 1

    collect.py run%%%%%/config.cym config*.cym
       will create directories run???? and copy the `config*.cym` files into them
    
F. Nedelec, 2012--2017. Last modified 2.10.2017