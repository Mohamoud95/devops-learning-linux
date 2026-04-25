# Level 6 to Level 7

## Goal
Locate a file somewhere on the server owned by a specific user and group, and of a precise size.

## Concept Explanation
Servers have thousands of files. Searching the entire filesystem requires managing permission errors (ignoring directories you don't have access to) and filtering by user/group ownership.

## Commands Used
- `find`, output redirection (`2>/dev/null`)

## What I Learned
I learned about standard error (`stderr`) redirection. Hiding permission denied errors made the search results actually readable.
