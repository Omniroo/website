---
title: "Pricing"
description: ""
layout: "pricing-custom"
---

{{< pricing-table-custom >}}
{
    "title": "Pricing",
    "description": "Flexible Pricing for Every Stage of Your SaaS Growth",
    "plans": [
        {
            "name": "Free",
            "price": "0",
            "priceSuffix": "/month",
            "description": "For new SaaS ventures setting up data visualization and pipeline management from day one",
            "features": [
                "1,000 sync events included",
                "Real-time sync of Stripe subscriptions into HubSpot deals pipeline",
                "Real-time sync of Stripe customers into HubSpot contacts",
                "Real-time sync of Stripe invoices into HubSpot invoices",
                "Custom mapping of subscription deal stages",
                "Usage alerts when approaching your monthly limit",
                "Automatic pause of syncs once the cap is reached"
            ],
            "button": {
                "text": "Get Started",
                "url": "https://app.omniroo.com/signup"
            }
        },
        {
            "name": "Pro",
            "price": "49",
            "priceSuffix": "/month",
            "description": "For growing SaaS companies refining their data-driven pipeline workflows to accelerate growth",
            "features": [
                "10,000 sync events included",
                "$0.01 per additional event",
                "Real-time sync of Stripe subscriptions into HubSpot deals pipeline",
                "Real-time sync of Stripe customers into HubSpot contacts",
                "Real-time sync of Stripe invoices into HubSpot invoices",
                "Custom mapping of subscription deal stages",
                "Usage notification on usage consumption",
                "Email support (48-hour SLA)",
                "Seamless syncing even if you exceed your monthly allowance"
            ],
            "button": {
                "text": "Choose Pro",
                "url": "https://app.omniroo.com/signup"
            }
        },
        {
            "name": "Business",
            "price": "299",
            "priceSuffix": "/month",
            "description": "For scaling SaaS companies expanding transaction volumes and advancing pipeline automation",
            "featured": true,
            "features": [
                "100,000 sync events included",
                "$0.005 per additional event",
                "Real-time sync of Stripe subscriptions into HubSpot deals pipeline",
                "Real-time sync of Stripe customers into HubSpot contacts",
                "Real-time sync of Stripe invoices into HubSpot invoices",
                "Custom mapping of subscription deal stages",
                "Usage notification on usage consumption",
                "Email support (48-hour SLA)",
                "Seamless syncing even if you exceed your monthly allowance"
            ],
            "button": {
                "text": "Choose Business",
                "url": "https://app.omniroo.com/signup"
            }
        },
        {
            "name": "Enterprise",
            "price": "Custom",
            "priceSuffix": "",
            "description": "For large SaaS organisations requiring tailored integrations, SLAs, and dedicated success plans",
            "features": [
                "Custom sync event allowance",
                "Custom overage pricing",
                "Real-time sync of Stripe subscriptions into HubSpot deals pipeline",
                "Real-time sync of Stripe customers into HubSpot contacts",
                "Real-time sync of Stripe invoices into HubSpot invoices",
                "Custom mapping of subscription deal stages",
                "Custom annual contract and usage",
                "Email (24-hour SLA) and video call support",
                "Dedicated Customer Success Manager",
                "Custom Success Program tailored to your business",
                "Seamless syncing even if you exceed your monthly allowance"
            ],
            "button": {
                "text": "Contact Sales",
                "url": "/enterprise-plan"
            }
        }
    ]
}
{{< /pricing-table-custom >}}

{{< faq >}}
{
    "title": "Common Questions",
    "description": "Find answers to frequently asked questions about our pricing plans and features.",
    "questions": [
        {
            "question": "What happens if I exceed the included sync events in my plan?",
            "answer": "If you're on the Pro, Business, or Enterprise plan, syncing continues without interruption. You'll be billed for additional Stripe events at your plan's overage rate."
        },
        {
            "question": "What happens when I hit the event cap on the Free plan?",
            "answer": "Once you reach the 1,000-event cap, syncing will pause automatically until the start of your next billing cycle. You'll receive alerts as you approach the cap."
        },
        {
            "question": "Can I upgrade or downgrade my plan at any time?",
            "answer": "Yes, you can change your plan anytime from your account dashboard. Upgrades take effect immediately. Downgrades take effect at the end of your current billing period."
        },
        {
            "question": "What counts as a \"sync event\"?",
            "answer": "A sync event corresponds to a Stripe event that's processed and synced into HubSpot. For example, an invoice may generate multiple Stripe events — such as `invoice.created`, `invoice.finalized`, and `invoice.paid` — each of which counts as a separate sync event."
        },
        {
            "question": "Do I need technical knowledge to set this up?",
            "answer": "No coding required. Setup is fast and intuitive, with a guided onboarding flow. Our support team is also available to assist if needed."
        },
        {
            "question": "Is there a trial for paid plans?",
            "answer": "You can start with the Free plan and upgrade when you're ready. If you'd like to evaluate a higher tier, reach out and we can arrange a trial or demo."
        },
        {
            "question": "Do you offer plans for agencies or partners?",
            "answer": "Yes. We support agencies, consultants, and platform partners with flexible pricing and onboarding support. Get in touch to learn more."
        },
        {
            "question": "What payment methods are accepted?",
            "answer": "We accept all major credit and debit cards via Stripe. Invoicing is available for Enterprise customers."
        },
        {
            "question": "Can I cancel anytime?",
            "answer": "Yes. You can cancel your subscription at any time. Your plan will remain active through the end of your billing cycle."
        }
    ]
}
{{< /faq >}}
