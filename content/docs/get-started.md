+++
date = '2025-07-05'
title = 'Get Started'
description = 'A guide to setting up and using the Stripe to HubSpot integration'
weight = 10
draft = false
type = 'docs'
menu = 'docs'
toc = true
tags = ['stripe', 'hubspot', 'getting started', 'setup']
categories = ['documentation']
+++

# Get Started with the Stripe to HubSpot Integration

This guide will walk you through the steps to set up and use the Omniroo Stripe to HubSpot integration.

## 1. Create a Project

*   [Sign up for an account at app.omniroo.com/signup](https://app.omniroo.com/signup).
*   Choose a plan that suits your needs.
*   [Configure your project](/docs/create-project):
    *   Name your project (e.g., "Marketing Automation").
    *   Set optional budget alerts (for paid plans).

## 2. Connect Stripe

*   Navigate to the "Sources" section in your project dashboard.
*   Create a Stripe source.
*   [Connect to Stripe](/docs/connect-stripe) using OAuth.
*   Select the Stripe account you want to connect and approve the requested permissions.

## 3. Connect HubSpot

*   Navigate to the "Destinations" section in your project dashboard.
*   Create a HubSpot destination.
*   [Connect to HubSpot](/docs/connect-hubspot) using OAuth.
*   Select the HubSpot portal you want to connect and approve the requested permissions.

## 4. Map Deal Stages

*   Navigate to the "Destinations" section and select your connected HubSpot destination.
*   Locate the "Subscription to Deal Stage Mapping" table.
*   [Map Deal Stages](/docs/map-deal-stage) to configure how Stripe subscription statuses and Price IDs map to HubSpot deal pipeline stages.
*   Remember to order your mappings from most specific to most general.

## Next Step
- [Understand Data Mapping](/docs/stripe-hubspot-data-mapping)

Need help? [Contact Support](/contact)
