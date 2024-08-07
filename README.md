# Swapped.com Pricing API

## Table of Contents
- [Swapped.com Pricing API](#swapped-pricing-api)
  - [Table of Contents](#table-of-contents)
  - [Version](#version)
  - [API Information](#api-information)
    - [URL](#url)
    - [Body Format](#body-format)
  - [Definition](#definition)
  - [Note](#note)
  - [Supported Payment Methods](#supported-payment-methods)
  - [Supported Fiat Currencies](#supported-fiat-currencies)
  - [Supported Crypto Currencies](#supported-crypto-currencies)
  - [Response](#response)
    - [Definition:](#definition-1)

## Version
1.0.1

## API Information

### URL
`https://eoats3bjlps5hvb.m.pipedream.net`

### Body Format

```json
{
  "payment_method": "creditcard",
  "fiat_currency": "EUR",
  "fiat_amount": 100, (Optional)
  "crypto_currency": "LTC",
  "crypto_amount": 1 (Optional)
}
```
## Definition

- `payment_method`: The selected payment method.
- `fiat_currency`: The selected fiat currency.
- `fiat_amount`: The fiat amount the customer wishes to pay.
- `crypto_currency`: The selected cryptocurrency.
- `crypto_amount`: If set, the calculation will be based on crypto amount instead of fiat amount.

**NB.** Body should either contain either `fiat_amount` or `crypto_amount`. If both are set, `crypto_amount` will overwrite `fiat_amount`.

## Note

Minimum order amount is 7 EUR, 8 USD, or other supported Fiat currency equivalent.

## Supported Payment Methods

| Supported `payment_method` | Supported `fiat_currency`                                                                                                        |
|----------------------------|----------------------------------------------------------------------------------------------------------------------------------|
| airtm                      | USD                                                                                                                              |
| apple-pay                  | EUR, DKK, USD, GBP, SEK, PLN, KZT, NGN, RON, ZAR, UAH, TWD, THB, CZK, TRY, CHF, INR, BRL, HUF, CAD, AUD, MXN, IDR, JPY, ILS, ISK, NZD, SGD, HKD, BGN |
| astropay                   | USD                                                                                                                              |
| bank-transfer              | EUR, DKK, USD, GBP, CAD, SGD, HKD, CHF, TRY                                                                                      |
| blik                       | PLN                                                                                                                              |
| paysafecard                | EUR, GBP, DKK                                                                                                                    |
| skrill                     | EUR, GBP, DKK                                                                                                                    |
| rapid-transfer             | EUR, GBP, DKK                                                                                                                    |
| neteller                   | EUR, GBP, DKK                                                                                                                    |
| giropay                    | EUR                                                                                                                              |
| epay                       | EUR                                                                                                                              |
| multibanco                 | EUR                                                                                                                              |
| mbway                      | EUR                                                                                                                              |
| rapid-transfer             | EUR                                                                                                                              |
| boleto                     | BRL                                                                                                                              |
| caixa                      | USD                                                                                                                              |
| creditcard                 | EUR, DKK, USD, GBP, SEK, PLN, KZT, NGN, RON, ZAR, UAH, TWD, THB, CZK, TRY, CHF, INR, BRL, HUF, CAD, AUD, MXN, IDR, JPY, ILS, ISK, NZD, SGD, HKD, BGN |
| dana                       | USD                                                                                                                              |
| google-pay                 | EUR, DKK, USD, GBP, SEK, PLN, KZT, NGN, RON, ZAR, UAH, TWD, THB, CZK, TRY, CHF, INR, BRL, HUF, CAD, AUD, MXN, IDR, JPY, ILS, ISK, NZD, SGD, HKD, BGN |
| ideal                      | EUR                                                                                                                              |
| interac                    | CAD                                                                                                                              |
| jeton                      | EUR, GBP, USD, CAD                                                                                                               |
| kasikornbank               | USD                                                                                                                              |
| mercadopago                | USD                                                                                                                              |
| mobilepay                  | DKK, EUR                                                                                                                         |
| neosurf                    | EUR, DKK, GBP                                                                                                                    |
| netbankingindia            | USD                                                                                                                              |
| ovo                        | USD                                                                                                                              |
| papara                     | TRY                                                                                                                              |
| parazula                   | TRY                                                                                                                              |
| payfix                     | TRY                                                                                                                              |
| pix                        | BRL                                                                                                                              |
| promptpay                  | USD                                                                                                                              |
| revolutpay                 | AED, AUD, BGN, CAD, CHF, CZK, DKK, EUR, GBP, HKD, HUF, ILS, ISK, JPY, MXN, NOK, NZD, PLN, RON, SEK, SGD, THB, TRY, USD, ZAR, JPY |
| spei                       | USD                                                                                                                              |
| tigerpay                   | JPY                                                                                                                              |
| upi                        | USD                                                                                                                              |

## Supported Fiat Currencies

| Currency |  |  |
| -------- | -------- | -------- |
| AED      | INR      | SGD      |
| AUD      | ILS      | THB      |
| BGN      | ISK      | TWD      |
| BRL      | JPY      | UAH      |
| CAD      | KZT      | USD      |
| CHF      | MXN      | ZAR      |
| CZK      | NGN      |          |
| DKK      | NOK      |          |
| EUR      | NZD      |          |
| GBP      | PLN      |          |
| HKD      | RON      |          |
| HUF      | TRY      |          |
| IDR      | SEK      |          |

## Supported Crypto Currencies

| Currency |     |     |
| -------- | --- | --- |
| BTC      | ETH | LTC |
| BCH      | XRP | DAI |
| DOGE     | LINK| USDT|
| USDC     | TRX | SOL |
| TON      |     |     |

## Response

```json
{
   "crypto_amount": "1.59397",
   "crypto_currency": "LTC",
   "crypto_unit_price": "60.30",
   "network_fee": "0",
   "fiat_amount_incl_fees": 100,
   "fiat_amount_excl_fees": "96.12",
   "fiat_currency": "EUR"
}
```
### Definition:
- `crypto_amount`: The crypto amount the customer would receive right now. Prices update every 10 sec.
- `crypto_currency`: The selected cryptocurrency.
- `crypto_unit_price`: The price for 1 of the selected cryptocurrency (In selected fiat).
- `network_fee`: The current network fee on the transaction (In selected fiat).
- `fiat_amount_incl_fees`: The amount the user will end up paying after fees (In selected fiat).
- `fiat_amount_excl_fees`: The amount you should parse to our payment window (In selected fiat).
- `fiat_currency`: The selected fiat.


