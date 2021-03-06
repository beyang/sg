# sg

A lightweight cli tool to interact with [Sourcegraph](https://sourcegraph.com).

## Installation

```bash
go get github.com/beyang/sg
```

## Configuration

You can configure `sg` to work with private [Sourcegraph](https://about.sourcegraph.com) instances in addition to Sourcegraph.com.

To do this, save a JSON file like the following to `~/.sg-config`:

```json
{
  "sourcegraphs": [
    {
      "url": "https://sourcegraph.mycompany.com",
      "repos": [
          "github.com/mycompany/private-repo",
          ...
       ]
    },
    ...
  ]
}
```

## Usage

```bash
sg [options] path/to/file
```

### Examples

#### Open a local file

```bash
sg main.go
```

#### Open a local file at a certain position

```bash
sg --line=22 main.go
# or
sg --line=22 --col=6 main.go
# or
sg --pos=22:6 main.go
```

#### Execute a search

```bash
sg --search="repo:gorilla/mux ^func Test"
```

#### Execute a search over the current repo

```bash
sg --search="^func main" .
```
