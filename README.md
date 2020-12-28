# Pashm-Html render Engine
The pashm-html is a engine to render pashmak code inside the Html/Text code.

For example:

```html
{
    $name = 'parsa'
}
<html lang="en">
<head>
    <title>Document</title>
</head>
<body>
    hello {{ $name }}
    { println('hello world') }
</body>
</html>
```

then we can render this code using this command:

```bash
$ pashmak pashmhtml.pashm myfile.html
```

output:

```html
<html lang="en">
<head>
    <title>Document</title>
</head>
<body>
    hello parsa
    hello world
</body>
</html>
```

this system can be used in web development.

Also you can use it in every text format, not only html.

for example:

```
{ $name = 'someone' }
hello {= $name }
```

output:

```
hello someone
```

## Usage
Usage of this system is very easy.

We have 2 statements:

- `{ code }`: runs a pashmak code between `{ }`
- `{{ <value-or-variable> }}` OR `{= <value-or-variable> }`: prints the value of between `{{ }}` or `{=  }`

for example:

```html
{
    $somevar = 'somevalue'

    func somefunc
        return 'hello somefunc'
    endfunc
}
<h1>Hello {= $somevar }</h1>
<h2>{= somefunc() }</h2>
```

output:

```html

<h1>Hello somevalue</h1>
<h2>hello somefunc</h2>
```

You only need to run:

```bash
$ pashmak pashmhtml.pashm /path/to/file.html
```

## Use as library
Also you can use this system as a library in your pashmak code.

Example:

```bash
import 'pashmhtml_core.pashm'

$output = pashm_html.run_file('/path/to/file.html')
$output = pashm_html.run('<code as string>')
```

The `run_file` function gets file path and runs that and returns the output.
`run` function gets code as string and runs that and returns the output.
