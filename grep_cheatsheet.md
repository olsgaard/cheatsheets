# GREP
g/re/p (globally search for a regular expression and print matching lines)

## Basic usage
Find lines containing pattern

```bash
grep 'my_pattern' myfile.txt
```

Find lines containing extended regex patterns. By default, grep only understands a very limited set of regex.

```bash
grep -E 'my_pattern' myfile.txt
egrep 'my_pattern' myfile.txt
```

## Find lines in folders

# Find pattern in files

Find static pattern, in all files

```bash
grep -r 'my_pattern' my/folder
```

## Find only pattern
It's generally not interesting to find a static pattern, so we add `-E` flag to be able to search for regex patterns.

```bash
grep -oE '[0-9]+' mynumbers.txt
grep --only-matching -E '[0-9]+' mynumbers,txt
```

## Find  non-matches

```bash
grep -vE '[0-9]' notnumbers.txt
```