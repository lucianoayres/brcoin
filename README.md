<p align="center"><img src="https://i.postimg.cc/8cjQJKVh/brcoin-logo.png" /></p>

<h2 align="center">Cryptocurrency prices in brazilian reais on command line</h2>

`brcoin` is an open source bash script to view cryptocurrency prices from Mercado Bitcoin public API on command line.

- Easy to use
- Setup & Run in seconds
- Get updated prices in brazilian reais (R$)

## Features

- 10+ listed cryptocurrencies
- Table view with multiple coins tracking 
- Raw price data you can integrate with your own project
- Price rounding and add currency symbol options
- Last, buy, sell, high, low and opening prices, and coin negotiated volume

`brcoin` runs on bash shell for Linux, Windows and Mac.

## Screenshot

<img src="https://i.postimg.cc/JhmMpCXx/screenshot.png" />

## Installation
### Step 1
Clone the project repository (or [download](https://github.com/esqb/brcoin/archive/main.zip) the script file):
```sh
$ git clone github.com/esqb/brcoin.git
```
### Step 2
Assign "execute" permission to the file:
```sh
$ sudo chmod +x brcoin
```
### Step 3
Add the script path to your $PATH (or simply move it to a folder already in your $PATH):
```sh
$ export PATH=$PATH:$PWD
```

## Dependency

Requires [jq](https://stedolan.github.io/jq/) to parse JSON data. Make sure to install it before running `brcoin`.

```sh
# install jq package on Ubuntu
$ sudo apt-get install jq
```

## Usage

```sh
# Display table view with all listed cryptocurrency prices 
$ brcoin
```

## Examples 

```sh
# Display table view with updated bitcoin price data
$ brcoin btc
```

```sh
# Display table view with Bitcoin Cash, Bitcoin, Ethereum and Link coin updated price data
$ brcoin bch btc eth link
```

```sh
# Display Litecoin raw updated price
$ brcoin ltc -r
```

```sh
# Display single view Ripple updated price data
$ brcoin xrp -single
```

```sh
# Display Bitcoin price data rounded to 2 decimal places with brazilian real currency symbol
$ brcoin btc -d2 -c
```

```sh
# display Bitcoin highest price of the day data
$ brcoin btc -r --high
```

```sh
# Display Ethereum rounded opening price of the day data with brazilian real currency symbol
$ brcoin eth -d -c --buy
```

## Options

brcoin [COIN] [VIEW MODE] [DATA TYPE]

### [COIN]
Sets a single or multiple cryptocoins ticker symbols.
Mandatory only when used combined with the folowing [VIEW MODE] types: raw, round, currency and single. If no [DATA TYPE] is set, --last is set by default.

| [COIN] | Description |
| ------ | ------ |
| bch |			Get Bitcoin Cash price |
| btc |			Get Bitcoi price |
| chz |			Get Chiliz price |
| eth |			Get Ethereum price |
| link |			Get Chainlink price |
| ltc |			Get Litecoin price |
| mco2 |			Get Moss Earth price |
| paxg |			Get PAX Gold price |
| usdc |			Get USD Coin price |
| wbx |			Get WBiX price |
| xrp |			Get Ripple price |

> Note: All prices in brazilian reais (R$).

### [VIEW MODE]
Optional argument to set the data output style to be displayed. If no [VIEW MODE] is set, --table is used by default. Raw, single and table view are exclusive and can not be combined with each other or any other available view mode. Round, -d and -d0 view modes can be combined with -currency view mode. 

| [VIEW MODE] | Description |
| ------ | ------ |
| -r, -raw |		Display raw price data |
| -d, -round |		Display rounded price data to 04 decimal places |
| -d2 |			Display rounded price data to 02 decimal places |
| -d0 |			Display rounded price data with no decimal places |
| -c, -currency |		Display raw price data with brazilian real currency symbol |
| -single |			Display all price data of the selected cryptocoin |
| -table |			Display selected cryptocoin(s) price data in table format |

### [DATA TYPE]
Optional argument to set the data items to be displayed in compatible [VIEW MODE] types: raw, rounded and currency. Only one [DATA TYPE] argument allowed per usage.

| Plugin | README |
| ------ | ------ |
| \-\-last |			Last price |
| \-\-buy	|		Buy price |
| \-\-sell |			Sell price |
| \-\-high |			Highest price of the day |
| \-\-low	|		Lowest prie of the day |
| \-\-open |			Opening price of the day |
| \-\-vol, \-\-volume |		Negotiated volume of the day |

## Additional Options

| Plugin | README |
| ------ | ------ |
| \-\-help |			Display command help |
| \-\-version |       Output version information |

# References

- [Mercado Bitcoin Data API](https://www.mercadobitcoin.com.br/api-doc/)
- Inspired by [coinmon](https://github.com/bichenkk/coinmon)

## License

[MIT License](https://github.com/esqb/brcoin/blob/main/LICENSE)
