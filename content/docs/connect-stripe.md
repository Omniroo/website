+++
date = '2025-07-05'
title = 'Connect to Stripe'
description = 'Guide to connecting your Stripe account to sync subscription data'
weight = 30
draft = false
type = 'docs'
menu = 'docs'
toc = true
tags = ['stripe', 'integration']
categories = ['documentation']
+++

# Connect to Stripe

## Before You Begin
- You'll need admin access to your Stripe account
- Ensure you have a project created in Omniroo
- Have your Stripe login credentials ready

## Connection Steps
1. **Navigate to Sources**
   - Go to your project dashboard
   - Click "Sources" in the left navigation

2. **Create a Stripe Source**
   - Click the "Create Source" button.
   - Select "Stripe" from the list of available source types.
   - A new Stripe source will be created, and you will be automatically redirected to its details page.

3. **Initiate Stripe Connection**
   - On the Stripe source details page, click the "Connect to Stripe" button.
   - You'll be redirected to Stripe's OAuth page

4. **Authenticate with Stripe**
   - Log in to your Stripe account
   - Select the Stripe account you want to connect
   - Review and approve the requested permissions

5. **Complete Connection**
   - You'll be redirected back to Omniroo
   - The connection will be verified automatically
   - You'll see a success message when complete

## What Gets Synced
By default, Omniroo will sync:
- Customers and their details
- Subscriptions and their status
- Invoices and payment history
- Line items in the subscriptions and invoices

## Next Step
- [Connect to HubSpot](/docs/connect-hubspot)

Need help? [Contact Support](/contact)
