# Cart Scraper

## What is it?

The cart scraper is an additional service provided by Fillr to extract key details from a user's ecommerce shopping cart in real time.

## Installation

```bash
npm i @fillr_letspop/cart-scraper
```

## Example Usage
- Require `@fillr_letspop/cart-scraper`
```javascript
const FillrScraper = require('@fillr_letspop/cart-scraper')
```

- Set dev key before calling `FillrCartInformationExtractionInterface.start()`

```javascript
window.FillrCartInformationExtractionInterface.setDevKey('YOUR_OWN_DEV_KEY');
```

- Define the event listener `onCartDetected()` 
```javascript
const onCartDetected = function(ev) {
  const cartInfo = ev.detail;
  console.log(JSON.stringify(cartInfo));
}
document.addEventListener('fillr:cart:detected', onCartDetected);
```

- start the cart information extraction
```javascript
window.FillrCartInformationExtractionInterface.start(); 
```

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

## License

[Copyright (c) 2015-present Pop Tech Pty Ltd.](LICENSE)