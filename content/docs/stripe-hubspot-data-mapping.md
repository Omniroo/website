+++
date = '2025-07-05'
title = 'Data Mapping Fields'
description = 'Understand how Stripe data maps to HubSpot and key fields for deduplication'
weight = 60
draft = false
type = 'docs'
menu = 'docs'
toc = true
tags = ['stripe', 'hubspot', 'mapping', 'deduplication']
categories = ['documentation']
+++

# Stripe to HubSpot Data Mapping and Deduplication

This document provides an overview of how Omniroo maps data from Stripe to HubSpot and the key fields used for deduplication. Understanding these mappings and deduplication keys is crucial for maintaining data integrity in your HubSpot portal.

## Important Deduplication Keys (Do Not Modify Manually)

Omniroo uses specific fields as unique identifiers to prevent duplicate records in HubSpot. **It is critical that you do NOT manually modify these fields in HubSpot**, as doing so can break the synchronization and lead to duplicate records or incorrect data.

## Object-Specific Mappings

### 1. HubSpot Object: Contact

Stripe customer data is mapped to HubSpot Contacts.

*   **Stripe Events Processed:** `customer.created`, `customer.updated`
*   **Stripe Fields Mapped to HubSpot Properties:**
    *   `data.object.email` → `email`
    *   `data.object.name` → `firstname` (first word of name)
    *   `data.object.name` → `lastname` (remaining words of name after the first)
    *   `data.object.phone` → `phone`
    *   `data.object.address.line1` → `address`
    *   `data.object.address.city` → `city`
    *   `data.object.address.state` → `state`
    *   `data.object.address.postal_code` → `zip`
    *   `data.object.address.country` → `hs_country_region_code`
*   **Deduplication Key:** `email` (from `data.object.email`). **Do NOT manually modify the `email` property in HubSpot for synced contacts.**

### 2. HubSpot Object: Deal

Stripe subscription data is mapped to HubSpot Deals.

*   **Stripe Events Processed:** `customer.subscription.created`, `customer.subscription.updated`, `customer.subscription.deleted`
*   **Stripe Fields Mapped to HubSpot Properties:**
    *   `data.object.id` → `dealname` (used as the primary identifier for the deal)
    *   Sum of (`data.object.items.data[*].price.unit_amount` * `data.object.items.data[*].quantity`) (sum of all subscription item amounts) → `amount` (converted from cents to dollars)
    *   `data.object.status` and `data.object.items.data[*].price.id` (price IDs of subscription items) → `pipeline` and `dealstage` (determined by your configured Pipeline Mapping Rules).
*   **Associations:**
    *   Associated with the relevant HubSpot Contact (found via `customerEmail`).
    *   Associated with HubSpot Line Items (created from `data.object.items.data`).
*   **Deduplication Key:** `dealname` (mapped from `data.object.id`). **Do NOT manually modify the `dealname` property in HubSpot for synced deals.**
    *   **Event Timestamp:** `last_processed:subscription:{data.object.id}`
    *   **Redis Locks:** `lock-{destinationID}:subscription:{data.object.id}` and `lock-{destinationID}:email:{customerEmail}`

### 3. HubSpot Object: Invoice

Stripe invoice data is mapped to HubSpot Invoices.

*   **Stripe Events Processed:** `invoice.created`, `invoice.updated`, `invoice.paid`, `invoice.payment_failed`, `invoice.finalized`
*   **Stripe Fields Mapped to HubSpot Properties:**
    *   `data.object.id` → `hs_title` (used as the primary identifier for the invoice)
    *   `data.object.status` → `hs_invoice_status` (mapped as follows: `draft`→`draft`, `open`→`open`, `paid`→`paid`, `void`→`voided`, `uncollectible`→`voided`, default to `draft`)
    *   `data.object.currency` → `hs_currency` (converted to uppercase)
    *   `data.object.total` → `hs_amount_billed` (converted from cents to dollars; only set for `draft` status invoices)
    *   `data.object.due_date` → `due_date` (formatted as "YYYY-MM-DD")
*   **Associations:**
    *   Associated with the relevant HubSpot Deal.
    *   Associated with HubSpot Line Items.
*   **Deduplication Key:** `hs_title` (mapped from `data.object.id`). **Do NOT manually modify the `hs_title` property in HubSpot for synced invoices.**

### 4. HubSpot Object: Line Item

Stripe line item data (from invoices and subscriptions) is mapped to HubSpot Line Items.

*   **Stripe Events Processed:** Handled as part of `invoice.*` and `customer.subscription.*` events.
*   **Stripe Fields Mapped to HubSpot Properties:**
    *   `data.object.lines.data[*].description` (for invoice events) OR `data.object.items.data[*].price.nickname` (for subscription events, falls back to `data.object.items.data[*].price.id`) → `name` (descriptive name, **not used for deduplication or correlation**)
    *   `data.object.lines.data[*].quantity` (for invoice events) OR `data.object.items.data[*].quantity` (for subscription events) → `quantity`
    *   `data.object.lines.data[*].amount` (for invoice events) OR `data.object.items.data[*].price.unit_amount` (for subscription events) → `price` (converted from cents to dollars)
    *   `data.object.lines.data[*].id` (for invoice events) OR `data.object.items.data[*].id` (for subscription events) → `hs_sku` (used as the primary identifier for the line item)
*   **Associations:**
    *   Associated with the relevant HubSpot Invoice.
    *   Associated with the relevant HubSpot Deal.
*   **Deduplication Key:** `hs_sku` (mapped from `data.object.lines.data[*].id` or `data.object.items.data[*].id`). **It is critical that you do NOT manually modify the `hs_sku` property in HubSpot for synced line items, as this is the unique identifier used for deduplication and correlation with Stripe product/price data.**

Need help? [Contact Support](/contact)
