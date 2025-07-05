+++
date = '2025-07-05'
title = 'Map Deal Stage'
description = 'Guide to mapping Stripe subscriptions and price IDs to HubSpot deal stages'
weight = 50
draft = false
type = 'docs'
menu = 'docs'
toc = true
tags = ['mapping', 'configuration']
categories = ['documentation']
+++

# Map Deal Stage

## Overview
Configure how Stripe subscription statuses and specific Price IDs map to HubSpot pipelines and deal stages. This allows you to precisely control how your subscription data is reflected in HubSpot.

## Mapping Steps
1. **Navigate to Destinations**
   - Go to your project dashboard.
   - Click "Destinations" in the left navigation.
   - Select your connected HubSpot destination.

2. **Access Mapping Table**
   - Within your HubSpot destination details, locate the "Subscription to Deal Stage Mapping" table.

3. **Add a New Mapping**
   - Click the "Add Mapping" button. A new row will appear for configuration.

4. **Configure Mapping Details**
   - **Order**: Use the up/down arrows to reorder mappings. Mappings are processed from top to bottom, and the first matching rule applies.
   - **Stripe Status**: Select a Stripe subscription status (e.g., `active`, `trialing`, `past_due`). This is the status of the Stripe subscription that will trigger this mapping.
   - **Price IDs**:
     - **None**: This mapping applies regardless of the Stripe Price ID.
     - **Any**: This mapping applies if the subscription includes *any* of the specified Price IDs. Enter multiple Price IDs separated by commas (e.g., `price_123, price_456`).
     - **All**: This mapping applies only if the subscription includes *all* of the specified Price IDs. Enter multiple Price IDs separated by commas.
   - **HubSpot Pipeline**: Enter the **Internal ID** of the HubSpot deal pipeline where the deal should be created or updated. You can find this in your HubSpot settings.
   - **HubSpot Stage**: Enter the **Internal ID** of the HubSpot deal stage within the selected pipeline. You can find this in your HubSpot settings.

5. **Save, Edit, or Delete Mappings**
   - **Apply**: Click "Apply" to save changes to an individual mapping.
   - **Cancel**: Click "Cancel" to discard changes to an individual mapping.
   - **Edit**: Click "Edit" on an existing row to modify its details.
   - **Delete**: Click "Delete" to remove a mapping.

## Best Practices
- **Order Matters**: Arrange your mappings from most specific to most general. For example, if you have a specific mapping for a "Free Trial" Price ID, place it above a general "Trialing" status mapping.
- **Comprehensive Coverage**: Ensure all relevant Stripe subscription statuses are covered by your mappings to avoid unmapped deals.
- **Validate Inputs**: Double-check that your HubSpot pipeline and stage internal IDs are exact matches to avoid sync errors.
- **Test Thoroughly**: After making changes, test with sample data to ensure deals are moving to the correct pipelines and stages in HubSpot.

## Next Step
- [Understand Data Mapping](/docs/stripe-hubspot-data-mapping)

Need help? [Contact Support](/contact)
