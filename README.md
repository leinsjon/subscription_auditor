# Subscription Auditor

A one-page, phone-friendly view of Jon's recurring charges. It shows the monthly total, a total per category, renewals sorted soonest first, a "still using this" toggle on each subscription, and a list of subscriptions that were turned off.

## Files

- `index.html` is the page. It has no build step and no dependencies.
- `subscriptions.json` is the data. Edit it to add, change or cancel a subscription.

## Data format

Each active subscription has `id`, `name`, `category`, `price`, `cycle` (`monthly` or `yearly`) and `renews` (a `YYYY-MM-DD` date, or `null` if unknown). Optional fields:

- `approx: true` shows the renewal as a month only.
- `expensed: true` lists it but leaves it out of the totals.
- `note` adds a line of text under the name.
- `source` records where the price came from: `receipt`, `market` or `you`.

Renewal dates roll forward on their own, so a monthly date in the past is shown as the next month's date.

To turn one off, move it from `active` to `cancelled` and give it an `ended` date.

The "still using this" toggles are saved in the browser on each device. They don't change the data file.

## Hosting

The page is served free by GitHub Pages from the repository root.
