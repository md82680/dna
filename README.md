# DNA Matching Program

This program identifies a person based on their DNA sequence by analyzing Short Tandem Repeats (STRs).

## Description

The program takes a DNA sequence and compares it against a database of people's DNA profiles by analyzing the consecutive repeats of specific STR sequences. It then identifies if the DNA sequence matches any person in the database.

## Usage

python3 dna.py database.csv sequence.txt

### Arguments
- `database.csv`: CSV file containing STR counts for a list of individuals
- `sequence.txt`: Text file containing the DNA sequence to identify

### Database Format
The database should be a CSV file with the following format:

name,AGATC,AATG,TATC

Alice,2,8,3

Bob,4,1,5

### Output
- If a match is found: Prints the name of the person
- If no match is found: Prints "No match"

## How it Works

1. **Command-line Validation**
   - Ensures correct number of command-line arguments
   - Verifies file accessibility

2. **Database Processing**
   - Reads the CSV database into memory
   - Extracts STR patterns from header

3. **DNA Analysis**
   - Reads the DNA sequence
   - For each STR pattern:
     - Finds the longest consecutive sequence of repeats
     - Stores the count for comparison

4. **Profile Matching**
   - Compares the DNA sequence's STR counts against each person in the database
   - Identifies exact matches across all STR patterns

## Functions

### `main()`
Orchestrates the overall program flow, including file reading and match identification.

### `longest_match(sequence, subsequence)`
Calculates the longest run of consecutive repeats for a given STR in the DNA sequence.

## Dependencies
- Python 3
- Standard libraries: `csv`, `sys`

## Example
$ python dna.py databases/large.csv sequences/5.txt

Lavender

## Error Handling
- Validates correct number of command-line arguments
- Handles file reading operations safely