# E-commerce Reporting & Auto-Reorder | Wildberries + Landing Store

**Role:** Automation developer, design and build
**Project type:** Real work for two online stores (a Wildberries store and a landing-page store), anonymized
**Tools:** Marketplace and store APIs · spreadsheets with live stock · Telegram Bot API

## The Challenge

Stock, orders and sales lived in separate tables. To understand what sells, what is running out and when to reorder, the owner had to merge everything by hand. Reorder decisions were late or based on guesswork, and it was hard to see which products were growing, which were falling and which ones were eating too much of the advertising budget.

## The Solution

1. **Unified data.** Spreadsheets with up-to-date stock were connected to order data and other data the owner needed, so one source of truth replaced several manual ones.
2. **Daily report in Telegram.** Data is pulled through the APIs and the owner receives a report every day automatically: sales and dynamics per SKU (what grows, what falls, which products spend too much of the advertising budget).
3. **Reorder table and automatic purchase orders.** A table shows reorder timing per product. The order is calculated so that stock covers 2 months and is sent to suppliers automatically. The owner only has to review the order and pay.

## What the owner got

- A daily report without opening a single spreadsheet
- Reorder deadlines visible per product
- Purchase orders prepared automatically; the only manual steps left are review and payment

## Notes

This is an anonymized description of real work: no client names, screenshots, credentials or revenue figures are published. The other case studies in this repository are built on a fictional store ("GearUp") with test data.
