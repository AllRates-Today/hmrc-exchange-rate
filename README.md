# HM Revenue & Customs Exchange Rates API — hmrc-exchange-rate

[![npm version](https://img.shields.io/npm/v/hmrc-exchange-rate.svg)](https://www.npmjs.com/package/hmrc-exchange-rate)
[![license](https://img.shields.io/npm/l/hmrc-exchange-rate.svg)](https://github.com/AllRates-Today/hmrc-exchange-rate/blob/main/LICENSE)
[![zero dependencies](https://img.shields.io/badge/dependencies-0-brightgreen.svg)](https://www.npmjs.com/package/hmrc-exchange-rate)
[![TypeScript](https://img.shields.io/badge/TypeScript-types%20included-3178C6.svg)](https://www.typescriptlang.org/)
[![GBP/USD today](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fallratestoday.com%2Fapi%2Fopen%2Fcentral-bank%2Fhmrc%3Fsource%3DGBP%26target%3DUSD&query=%24.rate&label=GBP%2FUSD%20published%20by%20HM%20Revenue%20%26%20Customs&color=0A7E8C&cacheSeconds=3600)](https://allratestoday.com/tax-authority-rates-api/hmrc/)
[![rate date](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fallratestoday.com%2Fapi%2Fopen%2Fcentral-bank%2Fhmrc%3Fsource%3DGBP%26target%3DUSD&query=%24.rate_date&label=rate%20date&color=555&cacheSeconds=3600)](https://allratestoday.com/tax-authority-rates-api/hmrc/)

**Official HM Revenue & Customs (the United Kingdom) monthly exchange rates for Node.js and TypeScript. The published tax authority rates behind tax filings, customs valuations, audits, and compliant invoicing — not market estimates, but the numbers HM Revenue & Customs itself prints, every month.**

## 🚀 Why this client?

- 🏛️ **Official published rates** — HM Revenue & Customs's own table, with the publisher's own `rate_date` on every response
- 📅 **History back to 2021** — point-in-time tables and daily series for any past date
- 🔀 **Published vs derived, always flagged** — computed inverse/cross pairs carry `derived: true`, never mixed with official prints
- ⚡ **Zero dependencies** — pure ESM + CJS over global `fetch`; Node 18+, Bun, Deno, and edge runtimes
- 🔷 **Type-safe** — full TypeScript definitions shipped with the package
- 🧾 **Compliance-grade metadata** — `rate_type`, publication date, and source disclaimer on every response

> **Official rate, not mid-market:** every value here is a number HM Revenue & Customs itself published, fixed once printed and carrying the tax authority's own `rate_date` — what filings and audits require. Need the live mid-market rate for pricing or display instead? Use the [mid-market API](https://allratestoday.com/docs/) or [`@allratestoday/sdk`](https://www.npmjs.com/package/@allratestoday/sdk). The two can diverge by several percent.

## ⚡ Try it without a key

The latest HM Revenue & Customs table is also served keyless, CORS-open and edge-cached, for evaluation, embeds and AI agents:

```bash
curl "https://allratestoday.com/api/open/central-bank/hmrc?source=GBP&target=USD"
```

```js
const r = await fetch('https://allratestoday.com/api/open/central-bank/hmrc').then((x) => x.json());
console.log(r.rate_date, r.rates.length); // the tax authority's latest published table, no key
```

The open endpoint serves the *latest* table only and asks for a visible attribution link. The client below uses the keyed API, which adds point-in-time tables, history, and CSV/XML/Excel output.

## 📈 Latest published table

Today's full HM Revenue & Customs table, straight from the tax authority's latest publication. On GitHub it is refreshed by [a daily Action](.github/workflows/daily-table.yml) that reads the keyless endpoint above and commits only when the tax authority publishes a new table; the copy on npm is as of the package's publish date.

<!-- daily-table:start -->
Published **2026-10-01** by HM Revenue & Customs — 141 rates, first 60 shown. Updated 2026-10-08.

| Base | Quote | Type | Rate |
| --- | --- | --- | ---: |
| GBP | AED | monthly | 4.9418 |
| GBP | ALL | monthly | 107.0437 |
| GBP | AMD | monthly | 489.0579 |
| GBP | AOA | monthly | 1233.1555 |
| GBP | ARS | monthly | 2027.5756 |
| GBP | AUD | monthly | 1.8868 |
| GBP | AWG | monthly | 2.4086 |
| GBP | AZN | monthly | 2.2875 |
| GBP | BAM | monthly | 2.2815 |
| GBP | BBD | monthly | 2.6912 |
| GBP | BDT | monthly | 165.6588 |
| GBP | BHD | monthly | 0.5059 |
| GBP | BIF | monthly | 4027.0511 |
| GBP | BMD | monthly | 1.3456 |
| GBP | BND | monthly | 1.7135 |
| GBP | BOB | monthly | 16.1986 |
| GBP | BRL | monthly | 6.927 |
| GBP | BSD | monthly | 1.3456 |
| GBP | BTN | monthly | 129.0581 |
| GBP | BWP | monthly | 18.1782 |
| GBP | BYN | monthly | 4.0782 |
| GBP | BZD | monthly | 2.7091 |
| GBP | CAD | monthly | 1.8758 |
| GBP | CDF | monthly | 3102.3658 |
| GBP | CHF | monthly | 1.102 |
| GBP | CLP | monthly | 1284.8396 |
| GBP | CNY | monthly | 9.0274 |
| GBP | COP | monthly | 4198.0295 |
| GBP | CRC | monthly | 602.5178 |
| GBP | CUP | monthly | 32.3035 |
| GBP | CVE | monthly | 128.6341 |
| GBP | CZK | monthly | 28.3582 |
| GBP | DJF | monthly | 239.61 |
| GBP | DKK | monthly | 8.7205 |
| GBP | DOP | monthly | 79.4809 |
| GBP | DZD | monthly | 179.9788 |
| GBP | EGP | monthly | 70.079 |
| GBP | ERN | monthly | 20.1842 |
| GBP | ETB | monthly | 217.507 |
| GBP | EUR | monthly | 1.1665 |
| GBP | FJD | monthly | 2.9777 |
| GBP | GEL | monthly | 3.498 |
| GBP | GHS | monthly | 15.4436 |
| GBP | GMD | monthly | 99.5772 |
| GBP | GNF | monthly | 11842.4924 |
| GBP | GTQ | monthly | 10.2705 |
| GBP | GYD | monthly | 281.4221 |
| GBP | HKD | monthly | 10.5562 |
| GBP | HNL | monthly | 36.152 |
| GBP | HTG | monthly | 175.9225 |
| GBP | HUF | monthly | 425.2162 |
| GBP | IDR | monthly | 23773.0976 |
| GBP | ILS | monthly | 4.0783 |
| GBP | INR | monthly | 129.0581 |
| GBP | IQD | monthly | 1763.3813 |
| GBP | ISK | monthly | 163.0905 |
| GBP | JMD | monthly | 212.3121 |
| GBP | JOD | monthly | 0.954 |
| GBP | JPY | monthly | 208.5932 |
| GBP | KES | monthly | 174.3866 |

[Full table on the HM Revenue & Customs rates page](https://allratestoday.com/tax-authority-rates-api/hmrc/) · Source: [Official rates published by HMRC, served by AllRatesToday](https://allratestoday.com/central-bank-rates-api/hmrc/). Rates are as printed by the tax authority; AllRatesToday is not affiliated with it.
<!-- daily-table:end -->

## 🔑 Get your API key

Get a free API key at [allratestoday.com/register](https://allratestoday.com/register) — no credit card required. Latest rates are on every plan, including free.

## 📦 Installation

```bash
npm install hmrc-exchange-rate
```

```bash
yarn add hmrc-exchange-rate
```

```bash
pnpm add hmrc-exchange-rate
```

Requires Node 18+ (global `fetch`); also runs on Bun, Deno and edge runtimes. Also published under the org scope as [`@allratestoday/hmrc-exchange-rate`](https://www.npmjs.com/package/@allratestoday/hmrc-exchange-rate) — same code, same versions.

## 🏁 Quick start

```js
import { getRate } from 'hmrc-exchange-rate';

const pair = await getRate('GBP', 'USD', { apiKey: 'art_live_...' });
console.log(pair.rate, pair.rate_date); // the official HM Revenue & Customs rate, on the tax authority's own date
```

## 📚 API reference

- [Latest pair rate](#latest-pair-rate) — one pair from the latest published table
- [Full published table](#full-published-table) — everything the tax authority printed, in one call
- [Table for a date](#table-for-a-date) — the official table for an invoice or filing date
- [Daily time series](#daily-time-series) — one pair across a date range

---

### Latest pair rate

Free plan and up. Pairs the tax authority does not print directly are resolved from its table and flagged (see *Published vs derived rates* below).

```js
const pair = await getRate('GBP', 'USD', { apiKey: 'art_live_...' });
```

**Response:**

```javascript
{
  bank: 'hmrc',
  name: 'HM Revenue & Customs',
  rate_date: '2026-10-01',   // HM Revenue & Customs's own publication date
  source: 'GBP',
  target: 'USD',
  rate: 1.3456,
  rate_type: 'monthly',
  derived: false,
  method: 'published',
  disclaimer: 'Official rates as published by the named central bank. On weekends/holidays the most recent published rate_date is returned.'
}
```

### Full published table

Free plan and up. The complete table for the latest publication date.

```js
import { getLatestRates } from 'hmrc-exchange-rate';

const table = await getLatestRates({ apiKey: 'art_live_...' });
console.log(table.rate_date, table.rates.length);
```

**Response:**

```javascript
{
  bank: 'hmrc',
  name: 'HM Revenue & Customs',
  rate_date: '2026-10-01',
  rates: [
    { "base": "GBP", "quote": "USD", "type": "monthly", "value": 1.3456 },
    // … the rest of the published table (141 currencies vs GBP)
  ],
  disclaimer: '…'
}
```

### Table for a date

Paid plans. The official table for any date since 2021 — weekends and holidays return the most recent published date, flagged via `published_on_requested_date`, which is exactly the in-force rate a filing needs.

```js
import { getRatesForDate } from 'hmrc-exchange-rate';

const day = await getRatesForDate('2026-06-30', { apiKey: 'art_live_...' });
// Optionally narrow to one pair:
const one = await getRatesForDate('2026-06-30', { apiKey: 'art_live_...', source: 'GBP', target: 'USD' });
```

**Response:**

```javascript
{
  bank: 'hmrc',
  requested_date: '2026-06-30',
  rate_date: '2026-06-30',                // the date actually published
  published_on_requested_date: true,      // false when a weekend/holiday fell back
  rates: [ /* the full table for that date */ ],
  disclaimer: '…'
}
```

### Daily time series

Paid plans. One resolved rate per publication date — ready for charting, revaluation runs, or audit workpapers.

```js
import { getHistory } from 'hmrc-exchange-rate';

const series = await getHistory(
  { source: 'GBP', target: 'USD', from: '2026-01-01', to: '2026-10-01' },
  { apiKey: 'art_live_...' }
);
```

**Response:**

```javascript
{
  bank: 'hmrc',
  source: 'GBP',
  target: 'USD',
  from: '2026-01-01',
  to: '2026-10-01',
  count: 152,
  rates: [
    // one entry per publication date
    { date: '2026-10-01', rate: 1.3456, rate_type: 'monthly', derived: false, method: 'published' },
    // …
  ],
  disclaimer: '…'
}
```

Pass `{ symbol: 'USD' }` instead of `source`/`target` to get the raw published rows for one currency (all rate types, no pair resolution).

---

## 🗺️ Currencies covered

HM Revenue & Customs currently publishes rates covering **141 currencies** against the GBP (as of the latest table):

🇦🇪 `AED` · 🇦🇱 `ALL` · 🇦🇲 `AMD` · 🇦🇴 `AOA` · 🇦🇷 `ARS` · 🇦🇺 `AUD` · 🇦🇼 `AWG` · 🇦🇿 `AZN` · 🇧🇦 `BAM` · 🇧🇧 `BBD` · 🇧🇩 `BDT` · 🇧🇭 `BHD` · 🇧🇮 `BIF` · 🇧🇲 `BMD` · 🇧🇳 `BND` · 🇧🇴 `BOB` · 🇧🇷 `BRL` · 🇧🇸 `BSD` · 🇧🇹 `BTN` · 🇧🇼 `BWP` · 🇧🇾 `BYN` · 🇧🇿 `BZD` · 🇨🇦 `CAD` · 🇨🇩 `CDF` · 🇨🇭 `CHF` · 🇨🇱 `CLP` · 🇨🇳 `CNY` · 🇨🇴 `COP` · 🇨🇷 `CRC` · 🇨🇺 `CUP` · 🇨🇻 `CVE` · 🇨🇿 `CZK` · 🇩🇯 `DJF` · 🇩🇰 `DKK` · 🇩🇴 `DOP` · 🇩🇿 `DZD` · 🇪🇬 `EGP` · 🇪🇷 `ERN` · 🇪🇹 `ETB` · 🇪🇺 `EUR` · 🇫🇯 `FJD` · 🇬🇪 `GEL` · 🇬🇭 `GHS` · 🇬🇲 `GMD` · 🇬🇳 `GNF` · 🇬🇹 `GTQ` · 🇬🇾 `GYD` · 🇭🇰 `HKD` · 🇭🇳 `HNL` · 🇭🇹 `HTG` · 🇭🇺 `HUF` · 🇮🇩 `IDR` · 🇮🇱 `ILS` · 🇮🇳 `INR` · 🇮🇶 `IQD` · 🇮🇸 `ISK` · 🇯🇲 `JMD` · 🇯🇴 `JOD` · 🇯🇵 `JPY` · 🇰🇪 `KES` · 🇰🇬 `KGS` · 🇰🇭 `KHR` · 🇰🇲 `KMF` · 🇰🇷 `KRW` · 🇰🇼 `KWD` · 🇰🇾 `KYD` · 🇰🇿 `KZT` · 🇱🇦 `LAK` · 🇱🇧 `LBP` · 🇱🇰 `LKR` · 🇱🇷 `LRD` · 🇱🇸 `LSL` · 🇱🇾 `LYD` · 🇲🇦 `MAD` · 🇲🇩 `MDL` · 🇲🇬 `MGA` · 🇲🇰 `MKD` · 🇲🇲 `MMK` · 🇲🇳 `MNT` · 🇲🇴 `MOP` · 🇲🇷 `MRU` · 🇲🇺 `MUR` · 🇲🇻 `MVR` · 🇲🇼 `MWK` · 🇲🇽 `MXN` · 🇲🇾 `MYR` · 🇲🇿 `MZN` · 🇳🇬 `NGN` · 🇳🇮 `NIO` · 🇳🇴 `NOK` · 🇳🇵 `NPR` · 🇳🇿 `NZD` · 🇴🇲 `OMR` · 🇵🇦 `PAB` · 🇵🇪 `PEN` · 🇵🇬 `PGK` · 🇵🇭 `PHP` · 🇵🇰 `PKR` · 🇵🇱 `PLN` · 🇵🇾 `PYG` · 🇶🇦 `QAR` · 🇷🇴 `RON` · 🇷🇸 `RSD` · 🇷🇺 `RUB` · 🇷🇼 `RWF` · 🇸🇦 `SAR` · 🇸🇧 `SBD` · 🇸🇨 `SCR` · 🇸🇩 `SDG` · 🇸🇪 `SEK` · 🇸🇬 `SGD` · 🇸🇱 `SLE` · 🇸🇴 `SOS` · 🇸🇷 `SRD` · 🇸🇻 `SVC` · 🇸🇿 `SZL` · 🇹🇭 `THB` · 🇹🇲 `TMT` · 🇹🇳 `TND` · 🇹🇴 `TOP` · 🇹🇷 `TRY` · 🇹🇹 `TTD` · 🇹🇼 `TWD` · 🇹🇿 `TZS` · 🇺🇦 `UAH` · 🇺🇬 `UGX` · 🇺🇸 `USD` · 🇺🇾 `UYU` · 🇺🇿 `UZS` · 🇻🇪 `VES` · 🇻🇳 `VND` · 🇻🇺 `VUV` · 🇼🇸 `WST` · `XAF` · `XCD` · `XOF` · `XPF` · 🇾🇪 `YER` · 🇿🇦 `ZAR` · 🇿🇲 `ZMW` · 🇿🇼 `ZWG`

## 🏛️ Source

HM Revenue & Customs is the United Kingdom's tax, payments, and customs authority. It publishes one official exchange rate table per calendar month — released ahead of the month it applies to — and that single rate is what UK customs declarations and VAT invoices must use for the whole month, regardless of how the market moves in between.

- Publisher's own page: [Monthly exchange rates for customs and VAT](https://www.trade-tariff.service.gov.uk/exchange_rates) · [www.gov.uk/government/organisations/hm-revenue-customs](https://www.gov.uk/government/organisations/hm-revenue-customs)
- Publication: every month; the exact schedule, freshness status and any current delay are on the [HM Revenue & Customs rates page](https://allratestoday.com/tax-authority-rates-api/hmrc/)
- Values are stored unmodified, with the publisher's own `rate_date` on every row — see the [methodology](https://allratestoday.com/official-rates-methodology/)

## 🧭 Reading the numbers

- `value` is always **quote currency per 1 unit of base currency** (`base: "EUR", quote: "USD", value: 1.15` means 1 EUR = 1.15 USD).
- HM Revenue & Customs quotes **foreign currency per 1 GBP** (e.g. `base: "GBP", quote: "USD"` means USD per one GBP).
- Need the other way round? Ask `getRate(target, source)` and the API inverts or crosses for you, flagged `derived: true` — never divide a published rate yourself in a compliance workflow.
- `rate_type` tells you which of the tax authority's series a row belongs to (`monthly` here); some publishers print buy/sell or several fixings for the same pair.

## 🧩 ERP & accounting systems

Loading the official HM Revenue & Customs rate into an accounting system is a supported workflow, not a hack. Step-by-step guides with the direction each system expects:

- [Dynamics 365 Business Central](https://allratestoday.com/docs/integrations/business-central/) — built-in Currency Exchange Rate Service, no code
- [Xero](https://allratestoday.com/docs/integrations/xero/) · [QuickBooks Online](https://allratestoday.com/docs/integrations/quickbooks/) · [SAP S/4HANA and ECC](https://allratestoday.com/docs/integrations/sap/) · [Odoo](https://allratestoday.com/docs/integrations/odoo/)

The same keyed endpoints return `?format=csv`, `?format=xml` and `?format=xlsx`, and accept the key as `?api_key=` on the URL for importers that cannot send headers:

```bash
curl "https://allratestoday.com/api/v1/central-bank/hmrc/latest?format=xml&api_key=art_live_..."
```

## 🤖 AI agents

- MCP server: `npx -y @allratestoday/central-bank-mcp` (stdio) or the hosted endpoint `https://allratestoday.com/api/mcp` — tools for official rates, history, cross-bank comparison and publication calendars
- Already using the general SDK or MCP server? Since 2026-10-01 [`@allratestoday/sdk`](https://www.npmjs.com/package/@allratestoday/sdk) 1.4+ has `officialRates('hmrc')` and [`@allratestoday/mcp-server`](https://www.npmjs.com/package/@allratestoday/mcp-server) 0.6+ has a `get_official_rates` tool — both return this source's latest table with no key, so you can add it without a second dependency
- Claude Code plugin (no key): `/plugin marketplace add AllRates-Today/claude-code-plugin` then `/plugin install allratestoday@allratestoday` — bundles both MCP servers plus an `/official-rate hmrc ...` command
- Machine-readable site guide: [llms.txt](https://allratestoday.com/llms.txt) · [for-ai-agents](https://allratestoday.com/for-ai-agents/)

## ⚖️ Published vs derived rates

If HM Revenue & Customs does not print a pair directly, the API resolves it from the tax authority's own table and says so — official and computed values are never confused:

| `method` | `derived` | Meaning |
| --- | --- | --- |
| `published` | `false` | The tax authority printed this pair directly |
| `inverse` | `true` | Computed as 1 ÷ the published opposite direction |
| `cross` | `true` | Computed via GBP from two published rates |

## 🛡️ Error handling

Errors are thrown as `Error` with `status` (HTTP code) and `body` (the API's JSON error) attached:

```js
try {
  const pair = await getRate('GBP', 'XXX', { apiKey: 'art_live_...' });
} catch (err) {
  console.log(err.message); // human-readable reason
  console.log(err.status);  // e.g. 404
}
```

| Status | Meaning |
| ------ | ------- |
| — | Missing `apiKey` (thrown before any request) |
| `400` | Malformed date or parameters |
| `401` | Invalid API key |
| `403` | Endpoint needs a [paid plan](https://allratestoday.com/pricing/) (historical dates & series) |
| `404` | Pair or date range not covered by HM Revenue & Customs |
| `429` | Monthly quota exceeded |

## 🔷 TypeScript

Full definitions ship with the package — no `@types` install:

```ts
import type { LatestRates, PairRate, DatedRates, RateEntry, HistoryQuery, RequestOptions } from 'hmrc-exchange-rate';
```

## 📦 CommonJS

```javascript
const { getRate } = require('hmrc-exchange-rate');

getRate('GBP', 'USD', { apiKey: 'art_live_...' }).then((pair) => console.log(pair.rate));
```

## 💡 Quota tips

- Rates change once a month — cache the published table locally and a small monthly quota goes a long way.
- Every request counts toward your AllRatesToday quota, shared across all AllRatesToday endpoints on your key.

## 📖 Methods reference

| Method | Plan | Description |
| ------ | ---- | ----------- |
| `getRate(source, target, { apiKey })` | Free | Latest rate for one pair, resolved from the published table |
| `getLatestRates({ apiKey })` | Free | The tax authority's full latest published table |
| `getRatesForDate(date, { apiKey, source?, target? })` | Paid | The official table (or one pair) for a YYYY-MM-DD date |
| `getHistory({ symbol \| source+target, from?, to? }, { apiKey })` | Paid | Daily series since 2021 |

## 📥 Bulk data (no key)

Need the whole archive rather than an API call? The same published tables are mirrored daily as open data:

- Hugging Face: [AllRates/central-bank-exchange-rates](https://huggingface.co/datasets/AllRates/central-bank-exchange-rates) — one CSV per institution (`rates/hmrc.csv`)
- Kaggle: [allratestoday/central-bank-exchange-rates](https://www.kaggle.com/datasets/allratestoday/central-bank-exchange-rates)
- CDN JSON: `https://cdn.jsdelivr.net/gh/AllRates-Today/central-bank-exchange-rates@main/data/hmrc/latest.json`

## 🔗 Links

- [HM Revenue & Customs rates page](https://allratestoday.com/tax-authority-rates-api/hmrc/) — live table, publication cadence, FAQ
- [All tax authority sources](https://allratestoday.com/tax-authority-rates-api/)
- [Package docs on the site](https://allratestoday.com/docs/sdk/hmrc-exchange-rate/) · [ERP integration guides](https://allratestoday.com/docs/integrations/)
- [API documentation](https://allratestoday.com/docs/#central-bank) · [Interactive reference](https://allratestoday.com/api-reference/) · [Methodology](https://allratestoday.com/official-rates-methodology/)
- [Register (free)](https://allratestoday.com/register) · [Pricing](https://allratestoday.com/pricing/)
- [GitHub](https://github.com/AllRates-Today/hmrc-exchange-rate)

## 📜 License

MIT
