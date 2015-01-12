yossarian-bot
=============

An entertaining IRC bot.

## Features:
* Unix fortunes (`fortune` must be present)
* Catch-22 quotes
* UrbanDictionary queries
* Wolfram|Alpha queries
* Weather updates
* Google searches
* Cleverbot
* ...and more!

## Running the bot

### Dependencies:
`yossarian-bot` depends on the `cinch`, `json`, `nokogiri`, `wolfram`,
`wunderground`, `xml`, `daemons`, and `cleverbot-api` gems.

To install them:

```bash
$ sudo gem install cinch json nokogiri wolfram wunderground libxml-ruby daemons cleverbot-api
$ # OR:
$ bundle install
```

`yossarian-bot` also requires API keys for several services. Make sure that
they are exported to the environment as follows:

* Wolfram|Alpha - `WOLFRAM_ALPHA_APPID_KEY`
* Weather Underground - `WUNDERGROUND_API_KEY`
* Merriam-Webster - `MERRIAM_WEBSTER_API_KEY`

Additionally, the `fortune` utility must be present in order for Unix fortunes
to work correctly.

### Installation
Once all dependencies (see above) are installed, simply clone the repo and
run `yossarian-bot.rb`:

```bash
$ git clone https://github.com/woodruffw/yossarian-bot
$ cd yossarian-bot
$ bundle install
$ ruby bot-control.rb start -- 'irc.example.net' '#chan1,#chan2'
$ # OR:
$ ruby yossarian-bot.rb 'irc.example.net' '#chan1,#chan2' # not run in background
```

## Using the bot

### Command-Line Options

* `-t`/`--no-link-titles` - Disable link titling.
* `-s`/`--no-seen` - Disable the `!seen` command.

`yossarian-bot` has two usage cases: commands and matches.

### Commands

There are a bunch of commands that `yossarian-bot` accepts. You can
see a complete list in the [COMMANDS](./COMMANDS.md) file.

### Matches

`yossarian-bot` matches all HTTP[S] links
and messages the title of the linked HTML page. This feature can be disabled
with the `-n`/`--no-link-titles` flag.

## License

`yossarian-bot` is licensed under the MIT License.

For the exact terms, see the [license](./LICENSE) file.
