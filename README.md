# MTG_Scrapper

A web scraper for Magic: The Gathering (MTG) cards that collects pricing and availability data from [cardmarket.com](https://www.cardmarket.com).

## Purpose

This project automates the collection of MTG card market data, including:
- Current selling prices (top 5 lowest offers)
- Available quantity on the market
- Average price trends (7-day average)
- Card images

This tool is particularly useful for:
- **Price tracking**: Monitor price fluctuations of specific cards over time
- **Deck building**: Check current prices for cards you want to add to your deck
- **Trading decisions**: Make informed buying/selling decisions based on market data
- **Collection management**: Track the value of your card collection

## Features

### Full Extension Scraping
The scraper can collect data for all cards from a specific MTG set (e.g., "Phyrexia: All Will Be One"), generating a comprehensive CSV file with market information for every card in the extension.

### Wishlist Mode
For more efficient tracking, you can specify a wishlist of cards you're interested in:
1. Edit `data/wishlist.txt` with your desired card names (semicolon-separated)
2. Run the wishlist scraper to generate a focused CSV with only your selected cards
3. Get faster results by avoiding unnecessary scraping of cards you don't care about

## Files

- **scrap.ipynb**: Main Jupyter notebook containing all scraping functions and logic
- **data/wishlist.txt**: Your custom list of cards to track (format: `Card1;Card2;Card3`)
- **data/wants.csv**: Generated CSV with pricing data for your wishlist cards
- **data/cards.csv**: Generated CSV with pricing data for all cards in an extension (when running full scraping)

## How It Works

The scraper:
1. Verifies cardmarket.com is reachable
2. Retrieves card listings from the target page(s)
3. For each card, extracts:
   - Card name
   - Top 5 lowest prices
   - Total quantity available
   - 7-day average price
   - Card image URL
4. Exports the data to a CSV file for easy analysis

## Usage

Open `scrap.ipynb` in Jupyter Notebook or JupyterLab and run the cells:

1. **Setup**: Install required dependencies (requests, beautifulsoup4, csv)
2. **Full Extension Scraping**: Uncomment and run the full extension scraping cell (~1h20min)
3. **Wishlist Scraping**: Edit `data/wishlist.txt`, then run the wishlist cells (~1-2 minutes)

## Example Output

The generated CSV files contain columns:
- Card Name
- Prices (list of 5 lowest prices)
- Quantity (total available on market)
- Average Price (7 days)
- Link to picture (full extension mode only)

## Requirements

- Python 3.x
- requests
- beautifulsoup4
- csv (standard library)
- os (standard library)
- re (standard library)

## Notes

- Processing time: ~1h20min for a full extension, ~1-2 minutes for a wishlist
- The scraper targets the French version of cardmarket.com (`/fr/`)
- All prices are in Euros (€)

## Example Wishlist

```
Captain Sisay;Reki,the History of Kamigawa;Elesh Norn, Mother of Machines;Atraxa, Grand Unifier
```

## Author

Alexandre Francony
