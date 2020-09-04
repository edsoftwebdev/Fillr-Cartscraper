# Cart Scraper


## Installation

```bash
$> npm install github:edsoftwebdev/Fillr-Cartscraper.git
```

## What is it?

The cart scraper is an additional service provided by Fillr to extract key details from a user's ecommerce shopping cart in real time.


## Exampe Cart Information JSON

```json
{
  "cart_total":2519,
  "currency":"USD",
  "id":"e14a939a-43a4-4e8e-81a7-6af50cbf10fd",
  "timestamp":1561984450662,
  "version":"1.3.35",
  "page_url":"https://www.amazon.com/gp/buy/spc/handlers/display.html?hasWorkingJavascript=1",
  "total_only":true,
  "is_cart":["buy"]
}
```

The `cart_total` value type of cart information represents as the number to avoid any floating rounding or precision issue. The `cart_total` works everything as cents. For example, USD 36.89 will be converted to integer value like USD 3689, which will preserve .89. The currency value follows the ISO 4217 code list like USD, EUR and SEK.

