---
title: "Throttling notifications across product, transactional, and marketing streams"
url: "https://www.courier.com/blog/notification-throttling-product-transactional-marketing"
date: "2026-04-16"
author: ""
feed_url: "https://www.courier.com/blog/feed"
---
A notification throttle that drops every event over a limit works fine for marketing nurtures and fails for product notifications, because product events carry context users actually need. The fix is pairing throttling with auto-batch: overflow events feed a batch node that rolls them up into a single digest, optionally rewritten by an AI node that prioritizes and summarizes the contents. This guide covers per-stream throttle setups for transactional, product, and marketing flows, and how the...
