# DOI Visualizer

#### Video Demo:
https://youtube.com/shorts/HcKnvVANlBY

#### Description:
This project visualizes DOI connections between academic papers...


# DOI Check Tool

## Description
This project is a DOI (Digital Object Identifier) checking tool.
It allows users to verify whether a DOI is valid and accessible.

The program sends a request to DOI resolving services and returns
information about the DOI status.

## Features
- Validate DOI format
- Check DOI accessibility
- Simple command line interface

## How to Use
1. Run the program
2. Enter a DOI
3. The tool will check whether the DOI exists

Example:

Input:
10.5281/zenodo.17173703

Output:
DOI is valid and reachable.

## Files
- main.py : main program
- checker.py : DOI validation logic
- README.md : project documentation

## Design Decisions
The program separates DOI validation and network checking
to make the code modular and easier to maintain.

# DOI Check Tool

## Description
This project is a DOI checking tool. It checks whether a DOI exists and can be resolved.

## Features
- Check DOI format
- Verify DOI accessibility

## Usage
Enter a DOI and the program checks if it is valid.

Example:
10.5281/zenodo.17173703

## Design
The program validates the DOI string and sends a request to a DOI resolver.

