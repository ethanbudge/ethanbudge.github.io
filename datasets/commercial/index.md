---
layout: page
title: Commercial Datasets
permalink: /datasets/commercial/
---
Paid datasets aimed at commercial use.

<ul class="dataset-list">
  {% for d in site.data.datasets.commercial %}
  <li class="dataset-card">
    <div class="dataset-card__info">
      <div class="dataset-card__title">{{ d.title }}</div>
      <p>{{ d.description }}</p>
      <div class="dataset-card__meta">{{ d.format }} &middot; {{ d.size }} &middot; {{ d.price }}</div>
    </div>
    <div class="dataset-card__action">
      <a class="btn btn--locked" href="{{ d.checkout_url }}">Buy</a>
    </div>
  </li>
  {% endfor %}
</ul>

To add a dataset, add an entry under `commercial:` in `_data/datasets.yml`,
with a `checkout_url` pointing at whatever paywall you end up using (see
below).

## Recommendation: how to paywall these without hosting a backend

This site is static (GitHub Pages) and has no server to gate downloads
itself, so the simplest and most secure approach is to hand payment *and*
file delivery to a third party built for exactly this, rather than rolling a
custom login/token system:

<div class="callout">
<strong>Recommended: <a href="https://gumroad.com">Gumroad</a></strong>
(or <a href="https://payhip.com">Payhip</a> as a close alternative) &mdash;
free to set up (they take a per-sale cut instead of a subscription), no code
required. You upload the dataset file there, set a price, and get a checkout
link to drop into <code>checkout_url</code> above. They handle payment
processing (PCI compliance is on them, not you) and only reveal/email the
download link after a successful payment, so there's no unpaywalled URL
sitting in this repo for anyone to find.
</div>

Why not roll your own gate: a "hidden" download link in a public GitHub repo
is not actually private (it's in the git history/build output regardless of
whether it's linked from the nav), and a real login system means you're now
responsible for authentication security, password storage, and payment
handling yourself. Gumroad/Payhip remove all of that for a standard revenue
cut and a five-minute setup.

If you outgrow that (e.g. you want usage-based pricing, licensing terms per
buyer, or your own checkout UI), the next step up without hosting your own
server is Stripe Payment Links + Stripe's hosted checkout, with the actual
file delivered via a signed, time-limited URL from a free-tier serverless
function (e.g. a Cloudflare Worker) that checks the Stripe payment webhook
before minting the link. That's meaningfully more setup for not much benefit
until you have a specific reason to need it.
