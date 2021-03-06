[![ghcal](http://i.imgur.com/yzElGZN.png)](#)

# `$ ghcal` [![Support this project][donate-now]][paypal-donations]

See the GitHub contributions calendar of a user in the command line.

If you want to track all your git commits (even if you don't push them anywhere), you should [check out the `git-stats` project](https://github.com/IonicaBizau/git-stats).

[![ghcal](http://i.imgur.com/OhgCb8o.png)](#)

## Installation

You can install the package globally and use it as command line tool:

```sh
$ npm i -g ghcal
```

Then, run `ghcal --help` and see what the CLI tool can do.

```sh
$ ghcal --help
Usage: ghcal [options]

Options:
  -u, --username <username>  The GitHub username. If you're using CLI GitHub,
                             by default it will be your username.            
  -c, --cookie <cookie>      Your GitHub cookie. Useful to get private stats.
  -s, --since <date>         Optional start date.                            
  -e, --until <date>         Optional end date.                              
  -n, --no-ansi              Forces the tool not to use ANSI styles.         
  -l, --light                Enables the light theme.                        
  -h, --help                 Displays this help.                             
  -v, --version              Displays version information.                   

Examples:
  ghcal -u ionicabizau
  ghcal -u ionicabizau --light
  ghcal -u ionicabizau --no-ansi
  ghcal -u ionicabizau -s '1 January 2015' # All the commits from 1 January 2015 to now
  ghcal -u ionicabizau -s '1 January 2015' -u '1 March 2015' # Select a time range

Note that only the last year statistics are available.

Documentation can be found at https://github.com/IonicaBizau/ghcal
```

## Usage
### Default behavior

If you are already using [`cli-github`](https://github.com/IonicaBizau/cli-github), then your GitHub username is kept into `~/.github-config.json` and `ghcal` will use it if you don't pass another username: `ghcal` will be the same with `ghcal -u <your-username>`.

```sh
ghcal
```
### Passing the username

 sing the `-u` (or `--username`) option, you can specify the GitHub username:

```sh
# Fetches the izuzak's contributions
$ ghcal -u izuzak
```
### Themes

If you pass the `--light` option, then the light theme will be activated (the default theme is dark).

```sh
# jlord's contributions, light theme
$ ghcal jlord --light
```
### No ANSI styles

The `--no-ansi` option disables any colors in the output. Unicode characters, without colors will be used.

```sh
# @pengywynn's contributions, but without ANSI styles
$ ghcal pengwynn --no-ansi
```

## Example

Here is an example how to use this package as library. To install it locally, as library, you can do that using `npm`:

```sh
$ npm i --save ghcal
```

```js
var GhCal = require("ghcal");

GhCal("ionicabizau", function (err, data) {
    console.log(err || data);
});
```

## Documentation

For full API reference, see the [DOCUMENTATION.md][docs] file.

## How to contribute
Have an idea? Found a bug? See [how to contribute][contributing].

## Where is this library used?
If you are using this library in one of your projects, add it in this list. :sparkles:

 - [`github-stats`](https://github.com/IonicaBizau/github-stats)

## License

[MIT][license] © [Ionică Bizău][website]

[paypal-donations]: https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=RVXDDLKKLQRJW
[donate-now]: http://i.imgur.com/6cMbHOC.png

[license]: http://showalicense.com/?fullname=Ionic%C4%83%20Biz%C4%83u%20%3Cbizauionica%40gmail.com%3E%20(http%3A%2F%2Fionicabizau.net)&year=2015#license-mit
[website]: http://ionicabizau.net
[contributing]: /CONTRIBUTING.md
[docs]: /DOCUMENTATION.md