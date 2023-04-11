# Movienator

A CLI to store simple information about movies

Uses sqlite as means of storage

## Usage
```
Usage: movienator <COMMAND>

Commands:
  add     Add a movie entry
  list    Print movie info
  remove  Remove a movie
  help    Print this message or the help of the given subcommand(s)

Options:
  -h, --help     Print help
  -V, --version  Print version
```

## Setup
The only prerequisite is having a `MOVIE_DATABASE_URL` environment variable. The [`setup.sh`](setup.sh) script will do that, though it may need some altering

Replace `~/.zshrc` with `~/.bash_profile` everywhere in the file if you don't have `zsh`

Execute with
```bash
$ zsh setup.sh # or bash
$ echo $MOVIE_DATABASE_URL
  sqlite:////Users/<username>/Documents/movies.db
```

## Example
```bash
$ movienator add "Cloud Atlas" -d 1970-01-01 -r 5
  "Cloud Atlas" has been added!

$ movienator add "Interstellar" -r 5
  "Interstellar" has been added!
  
$ movienator list
  You have 2 movies stored
  * | Cloud Atlas                             |  1970-01-01  |   5/5   | (no thoughts)
  * | Interstellar                            |   ________   |   5/5   | (no thoughts)
```

## What is This?
Just trying to pick up [`sqlx`](https://crates.io/crates/sqlx)

I'm especially proud of the `movienator list` command; its display formatting and broad search capability

And for how simple this is, it could be generalized to store more than movies. It really could store anything with a few modifications
