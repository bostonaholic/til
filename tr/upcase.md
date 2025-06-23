# Upcasing with `tr`

💡 `tr` translates characters from one set to another.

## Basic Usage

```bash
echo "hello world" | tr '[:lower:]' '[:upper:]'
# HELLO WORLD
```

## Character Classes

```bash
# Using POSIX character classes
echo "MiXeD CaSe" | tr '[:lower:]' '[:upper:]'
# MIXED CASE

# Using character ranges
echo "hello123" | tr 'a-z' 'A-Z'
# HELLO123
```

## Real World Example

Convert filenames to uppercase:

```bash
for file in *.txt; do
  mv "$file" "$(echo "$file" | tr '[:lower:]' '[:upper:]')"
done
```

💡 Unlike `awk` or `sed`, `tr` is specifically designed for character-by-character transformations, making it faster for simple case conversions.

## Useful Aliases

Add these to your `.bashrc` or `.zshrc` for quick case conversion:

```bash
alias upcase="tr '[:lower:]' '[:upper:]'"
alias downcase="tr '[:upper:]' '[:lower:]'"
```

Now you can use them like:

```bash
echo "make me loud" | upcase
# MAKE ME LOUD

echo "MAKE ME QUIET" | downcase
# make me quiet

# Chain them together
echo "MiXeD" | downcase | upcase
# MIXED

# Or with files
cat README.md | upcase
```

## Resources

[man tr](https://manpages.org/tr)

🎉 Happy coding!
