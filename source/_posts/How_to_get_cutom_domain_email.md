---
title: How to Get Your Custom Domain Email
date: 2024-11-29 14:00:00
tags: tech
---

# How to Get Your Custom Domain Email

## Why Use a Custom Domain Email?

Having an email address linked to your custom domain, like `you@yourdomain.com`, adds professionalism and a personal touch. It's a simple way to stand out from generic email addresses.

In this blog, I’ll show you how to set up your custom domain email for free using **Zoho Mail**, which provides up to 5 custom email accounts at no cost.

<!--more-->

## Step 1: Get a Custom Domain

First, you’ll need your own domain name. You can purchase one from any domain registrar, such as Namecheap, GoDaddy, or Google Domains.  
For this guide, I’ll use my domain: `namelessman.tech`.

## Step 2: Set Up Your Zoho Mail Account

1. **Register for a Zoho Mail Account**:  
   Go to [Zoho Mail](https://www.zoho.com/mail/) and sign up for an account. Choose the free plan to get started.

2. **Verify Your Domain**:  
   Follow Zoho's instructions to verify ownership of your domain.

3. **Update DNS Records**:  
   Log into your domain registrar's DNS management settings and add the following:

   - **MX Records**: These specify the mail servers responsible for receiving emails for your domain.
   - **TXT Records**: These are used for SPF (Sender Policy Framework), DKIM (DomainKeys Identified Mail), and DMARC (Domain-based Message Authentication, Reporting, and Conformance) to enhance email security.

   Zoho will provide the exact records you need to add. Be sure to follow their guidance step-by-step.

## Step 3: Start Using Your Email

Once everything is set up and verified, you can start sending and receiving emails from your custom domain. For example, I now use `namelessman@namelessman.tech`.

## Why Choose Zoho Mail?

- **Free Plan**: Perfect for personal use or small businesses with up to 5 users.
- **Professional Features**: Email hosting, calendars, and more, all integrated into one platform.
- **Affordable Expansion**: As your needs grow, you can upgrade to a paid plan for additional features.

## Costs Involved

The only expense here is the cost of purchasing a domain, which typically ranges from $10 to $15 per year. Zoho’s free plan means no additional costs for hosting your email.

## Try It Out!

If you’d like to test the setup, feel free to email me at 📧 [namelessman@namelessman.tech](mailto:namelessman@namelessman.tech).

<!-- <div id="domain-status">Checking domain status...</div> -->

<!-- <script>
(async function() {
  const domain = "mailto:namelessman@namelessman.tech";
  const statusElement = document.getElementById("domain-status");

  try {
    const response = await fetch(domain, { method: "HEAD", mode: "no-cors" });
    statusElement.textContent = "Domain is active ✅";
  } catch (error) {
    statusElement.textContent = "Domain is inactive ❌";
  }
})();
</script> -->

_<small>Written with assistance from ChatGPT</small>_
