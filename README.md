# ew
Local template engine script thingy

## This the code
```sh
#!/bin/sh

if [ ! -z "$TEMPLATES" ]; then
  printf 'bin/ew: TEMPLATES variable not set\n'
  exit 1
fi

if [ $# = "0" ]; then
  printf 'usage: ew <template_name>\n'
  exit 1
fi

template="$TEMPLATES/$1/main"
if [ ! -x "$template" ]; then
  printf 'bin/ew: template %s does not exist\n' "$1"
  exit 1
fi

shift
"$template" "$@"
```

## License
[MIT](https://tldrlegal.com/license/mit-license)
