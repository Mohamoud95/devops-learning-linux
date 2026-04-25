# Level 12 to Level 13

## Goal
Decompress a file that has been repeatedly compressed and archived using various algorithms (gzip, bzip2, tar) and represented as a hex dump.

## Concept Explanation
Files can be archived and compressed multiple times in different formats. You must iteratively determine the file type, reverse the hex dump, and apply the correct decompression tool.

## Commands Used
- `xxd`, `file`, `tar`, `gzip`, `bzip2`, `mv`

## What I Learned
This was a highly practical exercise in patience and file analysis. It taught me how to handle complex file archives and the importance of relying on the `file` command rather than file extensions.
