# Pondering PATH

## The PATH Variable

as done in the example, i blank out the path variable but running rm instead of ls before this time.

```
rm
ssh-entrypoint: rm: No such file or directory
PATH=""
```

this breaks rm, and we can just run /challenge/run to get the flag as c.

## Setting PATH

We set the PATH as the folder win is in, that is in /challenge/more_commands. we do this by doing **PATH=""**