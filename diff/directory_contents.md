# diff Directory Contents

Often times when I'm trying to clean up duplicate files in two directories, I append the output of `ls` to two files in each directory, then I run `diff` on those two files.

:bulb: `diff` can be used to find the difference in directory contents!

Not only will this find files that exist in one directory that don't exist in the other, it's more robust because it will also show me which files have changes; something that my previous method could not do.

`diff dir1 dir2`

## Resources

[man diff](https://manpages.org/diff)

:tada: Happy coding!
