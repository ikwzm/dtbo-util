dtbo-utils - Device Tree Blob Overlay Utility Programs
======================================================

# Overview

This repository provides utility tools for device tree overlays.
The following two utility tools are provided here.

 * dtbo-config  - shell script for creating or removing overlays in the linux device tree.
 * dtbo-compile - shell script for generating dtbo(device tree blob overlay).

# dtbo-config

```dtbo-config``` is a POSIX shell script for creating or removing overlays in the linux device tree.

## Usage

```console
shell$ dtbo-config --help
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
        List   : Print List of Device Tree Overlay Directory
        Status : Print Status of Device Tree Overlay Directory

OPTIONS
        -h, --help         Run Help    command
        -c, --create       Run Create  command
        -r, --remove       Run Remove  command
        -l, --load         Run Load    command
        -i, --install      Run Install command
        -t, --list         Run List    command
        -s, --status       Run Status  command
        -v, --verbose      Turn on verbosity
        -d, --debug        Turn on debug
        -n, --dry-run      Don't actually run any command
        --dts DTS          Device Tree Overlay Source File
        --dtb DTB          Device Tree Overlay Blob File

VARIABLES
        DTS                Device Tree Overlay Source File
        DTB                Device Tree Overlay Blob File
        DT_OVERLAY_NAME    Device Tree Overlay Name
        CONFIG_DTBO_PATH   Device Tree Overlay Configuration Path
                           Default='/config/device-tree/overlays/'
```

## Example

```console
shell$ dtbo-config --install argsort --dts argsort_16_2_2_5.10.dts
```

```console
shell$ dtbo-config --remove argsort
```

# dtbo-compile

```dtbo-compile``` is a Bourne-Again shell script for generating dtbo(device tree blob overlay).

## Usage

```console
shell$ dtbo-compile --help
NAME
     dtbo-compile - Device Tree Overlay Compiler

SYNOPSYS
     dtbo-compile [<options>] DTS...

DESCRIPTION
     Device Tree Overlay Compiler

OPTIONS
        -h, --help         Run Help    command
        -v, --verbose      Turn on verbosity
        -n, --dry-run      Don't actually run any command
        -P, --preprocess   Preprocess only; do not run DTC
        -k, --kernel <arg> Linux kernel source directory
        -K                 Linux kernel source directory is the current system
  GCC PreProcessor Options
        -i* args           This option is passed to gcc preprocessor
        -I*                This option is passed to gcc preprocessor
        -D*                This option is passed to gcc preprocessor
        -U*                This option is passed to gcc preprocessor
  DTC(Device Tree Compiler) Options
        -q, --quiet                
              Quiet: -q suppress warnings, -qq errors, -qqq all
        -o, --out <arg>            
              Output file
        -O, --out-format <arg>
              Output formats are:
              dts - device tree source text
              dtb - device tree blob
              asm - assembler source
        -d, --out-dependency <arg> Output dependency file
        -R, --reserve <arg>        
              Make space for <number> reserve map entries (for dtb and asm output)
        -S, --space <arg>          
              Make the blob at least <bytes> long (extra space)
        -p, --pad <arg>            
              Add padding to the blob of <bytes> long (extra space)
        -a, --align <arg>          
              Make the blob align to the <bytes> (extra space)
        -b, --boot-cpu <arg>       
              Set the physical boot cpu
        -f, --force                
              Try to produce output even if the input tree has errors
        -i, --include <arg>        
              Add a path to search for include files
        -s, --sort                 
              Sort nodes and properties before outputting (useful for comparing trees)
        -H, --phandle <arg>        
              Valid phandle formats are:
                      legacy - 'linux,phandle' properties only
                      epapr  - 'phandle' properties only
                      both   - Both 'linux,phandle' and 'phandle' properties
        -W, --warning <arg>        
              Enable/disable warnings (prefix with no-)
        -E, --error <arg>          
              Enable/disable errors (prefix with no-)
        -A, --auto-alias           
              Enable auto-alias of labels

VARIABLES
        DTS                      Device Tree Overlay Source File
        LINUX_KERNEL_SOURCE_PATH Linux kernel source directory
```

