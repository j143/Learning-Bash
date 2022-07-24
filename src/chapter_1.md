# Chapter 1

Creating a temporary directory:

```bash
mkdir temp
tmp_repo=$(mktemp -d temp/systemds-XXXXX)
```

This will generate a directory like `systemds-11ab8`, that is name with a random five digit string.

Run operations over a files in a directory with `for` loop

```bash
for file in $(find . -type f) # in the present directory (denoted by . ), search for type files (denoted by f) 
    do
      # remove any dots in the file name
      file_short=$(echo $file | sed -e "s/\.\///")

      # we can build a url format or any custom format
      dest_url="example.com/$file_short"
    done
```
