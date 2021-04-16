# Transact

Create a transaction around simple shell commands, so that differences
can be determined.

## Usage

Start a transaction around a command that outputs something you want to
compare, e.g. versions of packages:

```bash
transact start brew list --versions
```

This saves the output to a file in a central `transact` data directory.

Then perform your updates

```bash
brew upgrade
```

Compare with the previous output

```bash
transact diff brew
```

## Contributing

The project is built using Go. To contribute:

```bash
# fork project in github
git clone git@github.com:<username>/transact.git
cd transact
git remote add upstreammm https://github.com/mindriot101/transact.git
go test ./...
```

vim: tw=72
