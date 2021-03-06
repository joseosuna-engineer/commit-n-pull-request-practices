<img src="https://git-scm.com/images/logos/downloads/Git-Logo-2Color.png" align="right" width="300" />

# Git Commit Formatting Rules
> This is a guide to writte a Git commit message.

## Git commit message
> Build a subject / body Git commit message.

```bash
  commit d1674c5221ad87aa624a5029eb0c5db57b3eaf01
  Author: [removed]
  Date:   Sat Sep 12 09:13:24 2020 -0300

    This is the Git commit message subject

     - This is a Git commit message body line

```

### Subject
> Limit the subject line to 50 characters.
> Capitalize the subject line.
> Do not end the subject line with a period.
> Write your commit message in the **imperative**: "Fix bug" and not "Fixed bug" or "Fixes bug." This convention matches up with commit messages generated by commands like git merge and git revert.

#### Imperative mood:
  * Refactor
  * Update
  * Remove
  * Release
  * Merge
  
```bash
  commit d1674c5221ad87aa624a5029eb0c5db57b3eaf01
  Author: [removed]
  Date:   Sat Sep 12 09:13:24 2020 -0300

    Update getting started documentation

```

#### Body
> Wrap the body at 72 characters
> Use the body to explain what and why vs. how
> Always leave the second line blank.
> Further paragraphs come after blank lines.
> Typically a hyphen is used for the bullet, preceded by a single space.

```
  commit d1674c5221ad87aa624a5029eb0c5db57b3eaf01
  Author: [removed]
  Date:   Sat Sep 12 09:13:24 2020 -0300

    This is the Git commit message subject

     - Remove the 'state' and 'exceptmask' from serialize.h's stream
       implementations, as well as related methods.

     - As exceptmask always included 'failbit', and setstate was always
       called with bits = failbit, all it did was immediately raise an
       exception. Get rid of those variables, and replace the setstate
       with direct exception throwing (which also removes some dead
       code).

     - As a result, good() is never reached after a failure (there are
       only 2 calls, one of which is in tests), and can just be replaced
       by !eof().
    
     - fail(), clear(n) and exceptions() are just never called. Delete
       them.

```

## How to write a multiple line git commit message from command line

> Try the following to create a multi-line commit message:

```
git commit -m "This is the Git commit message subject" -m "- This is a Git commit message body line. 
- Add a title to your commit after -m enclosed in quotes, then add the body of your comment after a second -m.
- Press ENTER before closing the quotes to add a line break.
- Repeat as needed.
- Then close the quotes and hit ENTER twice to apply the commit."
```

