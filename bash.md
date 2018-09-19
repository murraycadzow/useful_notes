

## Less

To view a file at a particular line, and have line numbers on
```
less -N +<linenum> file
```

Other useful _less_ commands 
- -S # chops lines
- :g <linenum> # goes to line number
- -N # line numbers


## Cut

To extract the columns 1 to 10 from a file delimited by an underscore

- -f # the column range, leave the 'to' number off to get all remaining columns
- -d # specify the column delimiter. \t is the default

```
cut -f<from>-<to> -d"<delimiter>"
```
