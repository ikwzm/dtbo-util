dtbo-util - Device Tree Blob Overlay Utility Programs
======================================================

## dtbo-config

```console
shell$ ./dtbo-config --help
NAME
     ./dtbo-config - Device Tree Overlay Configure

SYNOPSYS
     ./dtbo-config [<options>] DT_OVERLAY_NAME

DESCRIPTION
     Device Tree Overlay Configure
        Create : Create Device Tree Overlay Directory
        Remove : Remove Device Tree Overlay Directory
        Load   : Load to Device Tree Overlay Directory
        Install: Create and Load

OPTIONS
        -h, --help         Run Help    command
        -c, --create       Run Create  command
        -r, --remove       Run Remove  command
        -l, --load         Run Load    comand
        -i, --install      Run Install command
        -v, --verbose      Turn on verbosity
        -d, --debug        Turn on debug
        -n, --dry-run      Don't actually run any command
        --dts DTS          Device Tree Overlay Source File
        --dtb DTB          Device Tree Overlay Blob File

VARIABLES
        DTS                Device Tree Overlay Source File
        DTB                Device Tree Overlay Blob File
        DT_DT_OVERLAY_NAME Device Tree Overlay Name
        CONFIG_DTBO_PATH   Device Tree Overlay Configuration Path
                           Default='/sys/kernel/config/device-tree/overlays/'
```
