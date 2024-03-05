# Troubleshooting

Troubleshooting is an essential skill for anyone who want to maintain an archlinux distro alive over a long period. Mostly it involves gathering relevant logs and asking smarter arch users, but most importantly...

```rust
# let x = "Read the fucking manual";
println!("{}", x);
```

## Gathering Logs

Here are some tips and tricks that will help with log gathering. When asking for help the [arch forums](https://bbs.archlinux.org/) is the best place. Don't get too upset if they insult your intelligence. The moderators are being asked the same old ignorant questions day in day out, and sometimes they lash out at good folks. This guide will prepare you such that you will not look like a fool.

#### Redirect _stdout_ to file

```sh
$ command > file
```

#### Append _stdout_ to file

```sh
$ command >> file
```

#### Redirect _stderr_ to file

```sh
$ command &> file
$ command 2> file
```

#### Append _stderr_ to file

```sh
$ command 2>> file
```

#### Both _stdout_ and _stderr_ to file **\***

```sh
$ command |& tee file
```

## Journalctl

#### Current boot

```sh
$ journalctl -b
```

#### Last boot (if after computer crash)

```sh
$ journalctl -b -1
```

#### File sharing from command line

```sh
$ journalctl -b | curl -F 'file=@-' 0x0.st
```

This will output a link with the log output which you can share on forums.
