# Downloads Organizer

A C# Application that runs in the background and organizes and watches the `~/Downloads` directory. The inital
run will determine if it needs to be organized, if so, it will create a respective container for each file
extension and automatically organize the downloads directory. Then,it will continue to run in the background 
and when a file is added into the `Downloads` directory, it is automatically organized into that respective 
container and if none exists, one is created for that extension type.

## Example:
```bash
    # original 
    Downloads/
    ├── test-dir/
    ├── hello.exe
    ├── goodbye.exe
    ├── bla.bla
    └── a.png

    # Automatic Organization
    Downloads/
    ├── folders
    │    └── test-dir
    ├── executables
    │    ├── hello.exe 
    │    └── goodbye.exe
    ├── bla
    │    └── bla.bla
    └── images
         └── a.png
         
    # Download bro.webp
    Downloads/
    ├── folders
    │    └── test-dir
    ├── executables
    │    ├── hello.exe 
    │    └── goodbye.exe
    ├── bla
    │    └── bla.bla
    └── images
         ├── a.png
         └── bro.webp
```

# Configurations

You can add or remove specific automatic categorizations. For example, by default, a images/ directory
will accept the generic, `webp, png, jpeg, jpg`. You can add onto this list and add on what is accepts.

Further containerizations can also be modified, like executables with the details of executables will be
autoamtically be put into exes/installations. Automatically, it checks for the words, "Setup", "Installer", 
"Install"

- Should support moving files from one watched directory to another. For example, files (i.e. mp3s) being watched in 
`Documents` and `Downloads` both go to `Documents/songs`