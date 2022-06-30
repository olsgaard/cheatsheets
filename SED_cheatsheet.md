# SED - Stream editor

## Search and replace, line by line

General usage pattern: `sed s/[pattern]/[replacement]/option`

```bash

# From STDIN
echo "day" | sed s/day/night/g # -> night

# From file
echo day > day.txt
sed s/day/night day.txt # -> night

```

### Replace only in lines given a criteria

You can have sed only do edits to lines that lives up to a search criteria like:

``` bash

echo "This is night\nThat is night" > night.txt

sed '/That/ s/night/day/g' night.txt # -> This is night
                                     #    That is day
```
