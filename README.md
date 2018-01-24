# Overview

This is a repository of API misuse bugs collected from previous papers on 
detecting anomolous program behaviors. The goal of this project is to amass 
a suite of bugs that can be used to provide a consistent benchmark for API 
misuse detection tools in the future.

# Project Structure 

## `./bugs`

This directory contains the necessary information to locate a bug found 
by a previous API misuse tool. The file format is as follows:

```yaml
name: Some descriptive name for the bug 
notes: General notes about the given bug
originator: 
  name: The tool that originally found this bug 
  details: A link to more details about the given bug (maybe a patch or CVE)
source:
  name: The actual source program the bug exists in (Linux/nmap/etc.)
  url: The url for the repository that contains the source program
  fixed_at: The hash of the commit that fixes the given bug (if applicable)
  exists_at: | 
  The hash of the commit that the given bug exists at. To be more precise, 
  checking out the source program at the given commit hash should leave the
  user with the source program in a state that contains the (unfixed) bug.
location:
  link: If possible, a link to (github/etc.) that helps to localize the bug
  file: The name of the source file the bug exists in 
  procedure: The name of the procedure in the source file that the bug is in
methods:
  - An 
  - array
  - of methods 
  - that relate to the given bug 
dockerfile: |
The path (relative to the root of this repository) of a Dockerfile that contains
a reproducible build of the source program in which the bug was found
```

## `./images`

This directory contains several Dockerfile's that, when built, provide 
self-contained Docker images that contain the source program and tools to 
build the source program.

