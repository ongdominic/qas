---
title: "Marketing website content design proposal"
source: claude.ai export 2026-11-20
chat_id: "01874384-c17d-4685-ac54-b4b43c2a06e5"
created: 2026-06-02T17:31+0800
updated: 2026-06-03T12:19+0800
messages: 31
vault: qas
project: "quality-air-solutions"
area_hint: "website-content / sales"
routing: confident
distilled: false
tags: [claude-import]
---
# Marketing website content design proposal

## Summary (from claude.ai)

**Conversation Overview**

The person is working on a marketing website for Quality Air Solution (QAS), a Singapore-based company and exclusive Airsmeg distributor across Singapore, Malaysia, and Indonesia. QAS sells three products on a rental-only, fully-maintained model: the Airsmeg AS-150 electrostatic air purifier, the Airsonic-QAS evaporative air cooler, and the KOMC kitchen oil mist collector. The person's role appears to be on the business/marketing side, coordinating website content and design for handoff to a designer or developer. The overarching brand promise established through the conversation is "Your air, our responsibility."

The session covered the full end-to-end content design and website prototype process: Claude analysed the company logo to extract exact brand colours (navy #0A1B3D, electric blue #1439F4, cyan #00B0F0), proposed a site architecture and content strategy, wrote placeholder and then real copy for all pages, built four fully responsive HTML prototypes (homepage, product page, segment/industry page, contact/quote page) using Schibsted Grotesk and Hanken Grotesk typefaces, and QA-rendered each via Playwright. Claude then read a sales playbook document to fill in confirmed AS-150 details — the complete 5-layer filtration system (pre-filter, electrostatic precipitator, active carbon, TiO₂ photocatalytic, UV-C), full specs including ~15W typical power, 99.9% efficiency to 0.01μm, noise levels, ionisation voltages, smart PM2.5 auto-sensor, and the 14-day free trial offer. A consolidated designer handoff document was maintained in both markdown and branded PDF format throughout.

Key decisions confirmed by the person: use +65 8188 9998 and sales@qas.sg sitewide; power is ~15W typical; adopt the playbook's "~30× finer than HEPA" framing (ozone stays omitted); pricing is not published on-site — conversion runs through the 14-day free trial (primary CTA on the AS-150 page) and enquiry; install time (~1 hour) and response time (next business day) are noted lightly on-site; HIP-specific angle is removed entirely; testimonials, Airsonic and KOMC product photography, and the final logo asset are to be provided later by QAS. The person consistently preferred Claude to build concrete deliverables and ask targeted clarifying questions rather than wait for direction, and appreciated when Claude flagged accuracy concerns (e.g. the unsupported "1.6-minute room clearance" claim and the 66W vs 15W discrepancy) before publishing. Outstanding work includes the Airsonic and KOMC product pages, whose specs and USP angles (energy savings and compliance/complaint-free respectively) are already documented in the handoff.

## Transcript

### Dom · 2026-06-02 17:31

can you go thru the materials in this folder around the 3 products and propose a content design for a marketing website to get people to enquire about the product. You can also look at the logo of the company and propose what colors would work for such a company. Really think thru and ask questions to get some clarifications

### Claude · 2026-06-02 17:34

> _tools used: view_

The uploads folder for this conversation is empty on my end — so before I dig in, let me check whether the materials live somewhere I can reach (like your Drive) and pull the product details I do have.

> _tools used: conversation_search_

I have solid background on QAS and the Airsmeg AS-150, but you mentioned **3 products** — and the uploads folder for this chat is empty on my end. Let me check your Drive for the folder.

> _tools used: tool_search_

I have detailed background on QAS and the **Airsmeg AS-150** from our earlier work together, but I want to flag something before diving in: the folder you're pointing at is empty on my end (nothing came through in this chat), and I don't have a Drive-browsing tool connected here. So I literally can't open the materials for the "3 products" — and I only have specs for one of them (the AS-150). I also can't see the logo file.

Let me at least peek at your live site to ground the color proposal in whatever brand cues already exist.

> _tools used: web_fetch, web_search_

Found your live site. Let me read it to see what's currently there — and whether it hints at the other two products.

> _tools used: web_fetch_

Good — I can now see your live site and I've located the logo. Let me actually look at the logo so my color recommendation is grounded in it rather than guesswork.

> _tools used: bash_tool, view_

Now let me pull the exact hex values from the logo so the palette is precise.

> _tools used: bash_tool_

I've got what I need to start properly. Here's where things stand and what I'm proposing — plus the questions that'll sharpen it.

## First, an honest gap

The folder came through empty on my side, and I don't have a Drive-browsing tool in this session, so I can't open the source materials directly. From our earlier work and your live site, I have full detail on **one** product — the Airsmeg AS-150 electrostatic precipitator (rental-only, 764 CMH CADR, filters down to 0.01μm, 5-stage system, SGS + CE certified). The other **two products you mentioned are new to me.** I'll flag below exactly what I need from you to fold them in.

## Colours — grounded in your actual logo

I pulled your logo off qas.sg and sampled it. It's a stylised bird/feather-in-flight made of two blues — a nice metaphor for clean air and lightness. The exact brand colours are:

- **Electric blue `#1439F4`** — your dominant logo colour. Vivid and confident, but very saturated, so it works best as the *action/brand* colour (buttons, links, highlights), not as a large background.
- **Sky cyan `#00B0F0`** — the accent stroke. Fresh, "clean-air" feel; great for icons, gradients, and the air-quality indicator motif.

To make those two usable as a full site palette, I'd extend them with anchors and neutrals:

- **Deep navy `#0A1B3D`** — for headers, text, and large dark surfaces. This grounds the electric blue and adds the premium/trustworthy weight a leasing brand needs.
- **Mist white `#F5F8FC`** and **cool grey `#E6EDF5`** — backgrounds and section separation; keeps it feeling clean and airy.
- **Slate `#48566B`** — body text (softer than pure black).
- Optional freshness accent — a restrained **mint/teal `#2FD4A8`** for "good air quality / eco" cues and the occasional pop beyond the blues. Only if you want warmth; the brand holds together fine as pure blue.

The two logo blues already form a natural gradient (cyan→electric), which I'd reuse as a signature hero treatment. Net direction: **trust + clean + fresh**, blue-led, navy-anchored, generous white space.

## Proposed content design (built to drive enquiries)

The single most important thing this site has to sell is not the machine — it's the **rental model**. "No capital outlay, maintenance and filter-cleaning handled by us, swap/upgrade anytime" is your real hook and also your biggest objection. The architecture below leads with that, and is structured as a **hub + spokes** so it scales cleanly to three products.

**1. Homepage (the hub)** — frames the problem, the rental value prop, and routes traffic:
- Hero: clean-air promise + dual CTA ("Get a free quote" / WhatsApp). Air-quality/haze framing for Singapore.
- "Why lease, not buy" — the differentiator, up high. No upfront cost, full maintenance, washable plates = never buy filters, upgrade flexibility.
- The 3 products as a comparison strip → each links to its own page.
- Trust band: SGS + CE certs, Made in Taiwan, exclusive SG/MY/ID distributor.
- "Who it's for" segment tiles → segment landing pages.
- Social proof (testimonials/logos — need material from you).
- Closing enquiry block.

**2. Three product pages (spokes)** — one per product, same template: hero image, what it's best for, specs table, the 5-stage system, certs, and an enquiry form pre-tagged to that product.

**3. Segment landing pages** — these are your paid-traffic and SEO catchers, and your site already hints at them via the BTO / Offices / HIP one-pagers: **HDB/BTO & renovation**, **Offices & commercial** (F&B, clinics, salons — renovation-formaldehyde angle), and **HIP (Home Improvement Programme)**. Each speaks the segment's language and funnels to enquiry.

**4. How it works** — the lease journey in 4 steps (enquire → free site assessment → install → we maintain). Removes friction and answers "what am I signing up for."

**5. Enquiry / Contact** — the conversion engine. I'd recommend: a short form (name, space type, approx. area, contact) **plus** prominent WhatsApp (your audience strongly prefers it), and offer a **free air assessment / site visit** as the lead magnet — much higher intent than "contact us."

A couple of ideas worth considering: a **lease-vs-buy savings calculator** (interactive, very persuasive for a rental model), and a short **haze-season** angle for seasonal campaigns.

## What I need from you

To actually go through the materials and build product pages for all three: could you **re-upload the brochures/catalogues into this chat** (or tell me the names and key specs of the other two products)? Right now I can only fully spec the AS-150. I can also pull the BTO / Offices / HIP PDFs from your site if that helps flesh out the segment pages.

And a few direction questions so the design fits your intent:

> _tools used: ask_user_input_v0_

> _[file: qas_logo.png, not included in export]_

### Dom · 2026-06-02 17:39

Q: Who's the priority audience for driving enquiries?
A: Both equally

Q: What's the main action you want a visitor to take?
A: Betwen 1 and 3

Q: What visual tone fits QAS best?
A: Clinical & trustworthy

### Claude · 2026-06-02 17:42

Both audiences, a dual "WhatsApp + free site assessment" conversion path, and a clinical/trustworthy tone — that's enough to firm up the design. Let me show you the colours applied to a homepage layout first, then give you the full content-design spec as a document.

> _tools used: visualize:read_me, visualize:show_widget_

That mockup captures the direction — clinical, trustworthy, blue-led, navy-anchored, with the lease model leading and a dual "book an assessment / WhatsApp" path. (The wing icon is just a stand-in; your actual bird logo would sit there.)

Now let me put the full content design into a document you can hand to a developer or stakeholders.

> _tools used: view, create_file, present_files_

That's the full proposal. A few things worth knowing as you take it forward:

The whole design leans on one strategic bet — that the **rental model is what you're really selling**, so it sits at the top of the homepage and gets its own page. That's also why the free site assessment is the headline action rather than a generic "contact us": it qualifies leads and works equally well for a homeowner and an office manager, which matches your "both audiences" answer.

The one real gap is **products 2 and 3** — I only have full specs for the AS-150, so those two cards are templated placeholders. If you re-upload the brochures here (or just tell me the names and key specs), I'll write those product pages to the same template and update the mockup.

A couple of optional next steps if useful: I can pull the BTO / Offices / HIP one-pagers from your live site to draft the three segment pages, or build out the lease-vs-buy savings calculator as a working interactive piece. And if you'd prefer this spec as a Word document for sharing, I can convert it.

### Dom · 2026-06-02 17:46

C:\Users\User\Documents\Claude\Projects\Quality Air Solutions in this folder there is a product folder that has the brouchure of the other 2 products. can you come up with the content strategy with just placeholder copy first?

### Claude · 2026-06-02 17:47

> _tools used: view_

Quick note: that path (`C:\Users\User\Documents\...`) is on your own computer, which I can't reach — I can only see files you upload into the chat, and nothing came through this turn. But that's fine for what you asked: here's the full content strategy with **placeholder copy** now, built so you can drop the real Product 2 and 3 details straight in once you upload those brochures (just drag the PDFs into the chat).

> _tools used: create_file, present_files_

Done — that's draft copy for every page, written to be used as-is where I have the facts (the AS-150 sections are real) and clearly bracketed everywhere I need your input.

The placeholders cluster around five things: Product 2 and 3 (names, specs, filtration, best-fit spaces), the AS-150's filtration stages 4 and 5, your maintenance/service details, pricing approach, and testimonials. The fastest unlock is the two brochures — drag those PDFs into the chat and I'll replace the Product 2/3 placeholders with real copy and refresh the homepage mockup to match.

One small judgment call I made: on the segment pages I guessed which unit suits which space (e.g. AS-150 for homes), but left the office/F&B recommendations as placeholders since the right answer depends on the other two products' coverage. Worth confirming once we have them.

### Dom · 2026-06-02 17:51

> _[file: AIRSONIC-QAS_DEBUT_FLYER 4 .pdf, not included in export]_

> _[file: KOMC catalogue.pdf, not included in export]_

### Claude · 2026-06-02 17:54

These two brochures change the strategy in a useful way — and it's worth flagging before I just swap in copy.

The three products aren't three air purifiers. They're three different "air jobs," which broadens who you're selling to:

1. **Airsmeg AS-150** — electrostatic *air purifier* (clean indoor air: homes, offices, clinics, salons)
2. **AIRSONIC-QAS** — evaporative *air cooler with dehumidifier effect* (cool large/open spaces: factories, warehouses, workshops, events, F&B, farms — ~80% less energy than aircon, made in Singapore)
3. **KOMC** — electrostatic *kitchen oil mist collector* (commercial kitchens: removes ~95% of oil mist and odour before discharge, so no neighbour complaints)

The thread tying them together is exactly your tagline — *"Your air, our responsibility."* All three are rental-only and fully maintained by QAS. So the site's real promise isn't "air purifiers" — it's **"we manage your air — clean, cool, or grease-free — on a lease, with servicing included."** That umbrella lets one brand sell to a homeowner, a factory, and a restaurant without feeling scattered.

Here's the now-real product range applied to the brand:

> _tools used: visualize:read_me, visualize:show_widget_

Now the full content strategy, updated with real copy for all three products and a revised structure that reflects the broader range.

> _tools used: create_file, present_files_

That's the full strategy with real copy for all three products now in place. The biggest change from the placeholder version is structural: because the range spans purifying, cooling, and kitchen oil-mist capture, the site is organised both **by product** and **by space/industry**, all sitting under the single "your air, our responsibility" promise — so a homeowner, a factory manager, and a restaurant owner each find their own path quickly.

A few honest notes on what I did and didn't do:

I deliberately framed Airsonic on cost, coverage, and sustainability rather than as a colder alternative to air-conditioning — it's evaporative cooling (24–26°C), and overpromising there would invite disappointed leads. Same sales-lens filtering you flagged before on the ozone row.

Two genuine things to resolve before this goes live: the brochures show **two different phone numbers** (8188 9998 on the purifier site vs 6665 1808 on the Airsonic/KOMC flyers) and two emails — you'll want one of each sitewide. And the AS-150's 5-stage filtration only had three stages spelled out in the materials I have; stages 4 and 5 are still bracketed.

The remaining placeholders are listed at the bottom of the doc. Want me to draft the Airsonic and KOMC product-page layouts as visuals too, or build out the lease-vs-buy savings calculator next?

### Dom · 2026-06-02 18:28

ok so how can we do this layout accurately so i can share this with e designer to build th website

### Claude · 2026-06-02 18:32

Good question — what you've got so far (content + a styled mockup) is great for *direction*, but a designer building the real thing needs something more precise: exact layout structure, the design tokens (colours, type scale, spacing, button styles), and every distinct page template. The most accurate, universally shareable form of that is a **responsive HTML prototype** — your designer can open it in a browser, inspect exact colours and spacing, and either rebuild it or use it as the starting point. It works whether they design in Figma or code directly.

Let me build that properly. I'll start with the homepage (it establishes every component — nav, buttons, cards, sections, footer), then we can extend to the product and contact templates.

> _tools used: view, create_file_

Let me quickly QA it by rendering to an image to catch any layout issues before I hand it over.

> _tools used: bash_tool, view_

Looks clean and on-brand. Let me confirm it holds up on mobile too.

> _tools used: bash_tool, view_

Solid on mobile — nav collapses to a menu, everything stacks cleanly. One small flaw: the "Get a quote" button loses its label on the narrowest screens and shows as an empty pill. Let me fix that.

> _tools used: str_replace, present_files_

Here's the accurate, shareable version. Your designer can open this `.html` in any browser, resize it to see the responsive behaviour, and use browser dev-tools to read off exact colours, spacing, and fonts — it's a working prototype, not just a picture.

What makes it a proper handoff:

The design tokens are defined once at the top of the file (`:root`) — every brand colour, the type scale, spacing, and corner radius. That block *is* the style guide; a designer rebuilds from those values. It uses your real logo and brand blues (navy `#0A1B3D`, electric `#1439F4`, cyan `#00B0F0`), a clean clinical/trustworthy type pairing (Schibsted Grotesk + Hanken Grotesk), and every reusable component the rest of the site needs: sticky nav, the three button styles, solution cards, feature blocks, industry tiles, the numbered "how it works" steps, footer, and the floating WhatsApp button. Placeholders are marked in `[brackets]`, and section labels in the code tell the designer what each block is.

Two practical notes for whoever builds it:
- I used **+65 6665 1808** and **sales@qas.sg** throughout as a single contact set — swap if you'd rather standardise on the other number/email.
- This one page establishes the full design language. The **product page**, **industry/segment page**, and a proper **contact form page** reuse these same components — I can build those three templates next so your designer has the complete set, or convert the whole thing into a short PDF spec sheet (tokens + screenshots + annotations) if they'd prefer a document alongside the code.

Want me to build out those remaining page templates?

> _[file: qa_full.png, not included in export]_

> _[file: qa_mobile.png, not included in export]_

### Dom · 2026-06-02 18:39

yes please

### Claude · 2026-06-02 18:41

On it. I'll build the three remaining templates — product page, industry/segment page, and contact/quote page — using the exact same design system so they're a consistent set, then QA-render each.

> _tools used: create_file_

### Dom · 2026-06-02 19:53

cont

### Claude · 2026-06-02 19:56

Continuing — now the industry/segment page (F&B & commercial kitchens, showing how a segment pairs two products), then the contact/quote page.

> _tools used: create_file_

Now the contact / get-a-quote page — the conversion engine.

> _tools used: create_file_

Now let me QA-render all three to catch any layout issues.

> _tools used: bash_tool, view_

The product page renders beautifully — real product photo, clean two-column spec table, filtration stages (with stages 4–5 clearly marked as to-confirm). Let me check the segment page.

> _tools used: view_

Segment page is clean — the KOMC + AS-150 pairing reads clearly with the "best for the kitchen / dining area" tags. Now the contact page.

> _tools used: view_

All three render cleanly and consistently with the homepage. Here's the complete set.

> _tools used: present_files_

You now have the four core templates a designer needs to build the whole site:

- **Homepage** — the hub and full design language
- **Product page** (AS-150 example) — spec table, five-stage filtration, certifications, related products
- **Industry/segment page** (F&B & kitchens example) — shows how a segment pairs two products
- **Contact / get-a-quote page** — the styled enquiry form plus direct WhatsApp/email

A few things that make this an easy handoff: all four share one identical design-token block (`:root`), so the system is consistent and documented in the code itself. The pages **cross-link** — click "Get a quote," a product card, or a segment tile and you'll move between them — so keep all four files in the same folder when you open or send them. The product and segment files have header comments explaining how to duplicate them for the remaining products and segments (e.g. copy the product page, swap the hero/specs/image for Airsonic and KOMC).

Two things still need you before build: the **contact form is front-end only** — your developer wires submission to email or a CRM — and the placeholders remain (AS-150 filtration stages 4–5, lead time, response time, pricing approach, and the single phone/email to standardise on).

If it's helpful for the designer, I can package this into a short **PDF spec sheet** (the palette, type scale, spacing, button styles, and screenshots with annotations) to sit alongside the code — or build the actual Airsonic and KOMC product pages so all three are done. Which would move you forward more?

> _[file: qa_qas_product_prototype.png, not included in export]_

> _[file: qa_qas_segment_prototype.png, not included in export]_

> _[file: qa_qas_contact_prototype.png, not included in export]_

### Dom · 2026-06-02 19:58

in this page can we talk about the USP of the product

### Claude · 2026-06-02 20:00

Quick check on which page — I'll assume you mean the **product page** (the AS-150), since that's where a unique-selling-point section earns its place. Tell me if you meant another one.

For the AS-150, the strongest USP isn't any single spec — it's the *combination* of the electrostatic technology with the rental model: washable plates mean no filters to buy, and because it's leased and maintained, QAS does the cleaning. So the customer gets high-grade air cleaning with nothing to buy, replace, or maintain. That's the angle I'll lead with. Let me add a dedicated section to the product page.

> _tools used: str_replace, bash_tool, view_

The navy USP band reads well after the hero. Let me see the full band with the four cards.

> _tools used: bash_tool, view_

The USP band is in. Here's the updated product page.

> _tools used: present_files_

I added a **"What makes it different"** band right after the hero — a navy section so it stands out as the persuasion peak of the page, before the specs back it up. It leads with the core USP and supports it with four points:

- **Captures the ultrafine** — filters down to 0.01μm, far smaller than the PM2.5 most purifiers are measured against.
- **No filters to ever buy** — washable electrostatic plates instead of disposable filters.
- **We maintain it for you** — because it's leased, QAS cleans the plates on schedule.
- **Clears a room in minutes** — 764 CMH with 360° circulation refreshes 50m² in ~1.6 minutes.

The strategic point is the first three working together: the electrostatic tech removes the recurring filter cost, and the rental model removes the upkeep — so the real selling line is "high-grade air cleaning with nothing to buy, replace, or maintain." That's hard for a buy-it-yourself purifier to match.

One thing I deliberately avoided: I didn't frame it as "better than HEPA," since HEPA also captures sub-micron particles and that claim invites pushback — same sales-lens caution as the ozone row from before. The 0.01μm-vs-PM2.5 framing is accurate and still lands as a strength.

Each product has a different USP centre of gravity — Airsonic's is the ~80% energy saving and wide-area coverage; KOMC's is the 95% oil-mist removal and 8-minute servicing that keeps you complaint-free. Want me to build those two product pages with their own USP bands, following this same pattern?

> _[file: qa_usp.png, not included in export]_

> _[file: qa_usp2.png, not included in export]_

> _[file: qa_usp3.png, not included in export]_

> _[file: qa_usp4.png, not included in export]_

### Dom · 2026-06-02 20:05

nice this looks great. can you put it into a content strategy doc as well so that i can share with a designer

### Claude · 2026-06-02 20:06

Absolutely. I'll consolidate everything — the positioning, the design system, the page-by-page copy, and a USP section for all three products — into one handoff doc that sits alongside the HTML prototypes.

> _tools used: create_file, present_files_

This version is the one to hand over — it consolidates everything into a single designer-ready reference and pairs with the four HTML prototypes.

What's new versus the earlier strategy docs: it now includes the **design tokens** (colours, fonts, type scale, components) so the system is documented in the doc itself, a **USP band for all three products** (not just the AS-150 — I wrote Airsonic's around the ~80% energy saving and KOMC's around the 95% oil-mist removal and 8-minute servicing), and a **file map** at the end so the designer knows which prototype is which and how to extend them.

I kept the same sales-lens guardrails written into the voice section, so whoever edits the copy later doesn't reintroduce the "better than HEPA" or "colder than aircon" claims.

Two formats if useful: I can convert this to a **Word document** (often easier for a designer to comment on), or fold it plus annotated screenshots into a single **PDF spec sheet**. And the obvious next build step is the Airsonic and KOMC product pages — the USP copy for both is already written in this doc, so I'd just drop it into the template. Want me to do either?

### Claude · 2026-06-02 23:56

Absolutely. I'll consolidate everything — the content strategy, the design system from the prototypes, the page layouts (including the new USP band), and each product's USP angle — into one handoff document a designer can work from alongside the HTML files.

> _tools used: create_file, present_files_

This consolidates everything into one designer-ready document. It pulls together the content strategy, the design system (exact colour tokens, type scale, spacing, components — lifted straight from the prototypes so they match), the page-by-page layouts including the new USP band, and — importantly — each product's distinct USP angle so whoever writes the Airsonic and KOMC pages knows what to lead with (AS-150 = nothing to maintain; Airsonic = energy savings; KOMC = staying complaint-free).

It's designed to sit beside the four HTML files: the doc explains the *what and why*, the prototypes show the *how it looks*. Section 1 maps which file is which, and the open-items list at the end is the short punch-list of things only you can confirm before build (the duplicate phone/email, filtration stages 4–5, pricing approach, photos).

If your designer would prefer this as a polished **Word document or PDF** rather than markdown, I can convert it — and I can still build out the Airsonic and KOMC product pages so the full set of three is ready. Just say which.

### Dom · 2026-06-02 23:59

can i get access to the HTML file?

### Claude · 2026-06-02 23:59

You already have them — they're the files I shared in the messages above (each appears as a downloadable/clickable card). But let me re-present all of them together here so they're easy to grab in one place.

> _tools used: present_files_

Here's the full set:

- **qas_homepage_prototype.html** — homepage
- **qas_product_prototype.html** — product page (AS-150, with the USP band)
- **qas_segment_prototype.html** — industry/segment page
- **qas_contact_prototype.html** — contact / get-a-quote page
- **QAS_Content_Design_Handoff_v3.md** — the written handoff doc

To open them: tap a card to download (or click through to preview). A couple of practical tips — **keep all four HTML files in the same folder** so the cross-links between pages work, and just double-click any of them to open in a browser. To zip them into a single file, or to bundle everything into one downloadable package for your designer, let me know and I can set that up.

### Dom · 2026-06-03 00:04

can you this document to update the misisng content for Airsmeg

> _[file: QAS_Sales_Script_Playbook_ Eng .docx, not included in export]_

### Claude · 2026-06-03 00:04

I'll read the sales playbook and pull out the details that fill the AS-150 gaps (filtration stages 4–5, maintenance, lead time, etc.), then update the product page. Let me start by checking how to read the doc properly.

> _tools used: view, bash_tool_

### Dom · 2026-06-03 09:29

cont

### Claude · 2026-06-03 09:32

This playbook has exactly what I needed — the full 5-layer breakdown, real specs, and a documented USP set. Let me look at the current product page sections I need to update.

> _tools used: view_

Now I'll update the page with the authoritative content. First the hero line and key-spec chips:

> _tools used: str_replace_

Now the spec table with the full authoritative figures:

> _tools used: str_replace_

Now the complete 5-layer filtration (no more placeholders):

> _tools used: str_replace_

Now expand the best-fit tags to the environments the playbook documents:

> _tools used: str_replace_

Let me QA the updated page.

> _tools used: bash_tool, view_

All the placeholders are now filled with real, sourced content. Here's the updated product page.

> _tools used: present_files_

The playbook filled every AS-150 gap. What changed on the page:

- **Five-layer filtration** is now complete and correct — pre-filter → electrostatic precipitator → active carbon → photocatalytic (TiO₂) → UV-C — plus the optional pet pre-filter and negative-ion note. (The earlier order was slightly off; this matches the playbook.)
- **Spec table** is now fully authoritative: 99.9% to 0.01μm, three-speed airflow (765/586/314 m³/h) and noise (49/45/40 dB), dimensions, 71 plates at 4mm pitch, ionisation voltages, the smart PM2.5 sensor, 4-stage touch + remote, and the four SGS scopes.
- **USP band** sharpened with the documented USPs — I swapped the weakest card (an unsupported "1.6-minute" speed claim) for the **smart PM2.5 sensor / auto fan speed**, which is one of their strongest differentiators, and corrected the filter card to "no filter *bills*" since the unit does use carbon/TiO₂ filters — they're just covered by the lease.
- **Best-fit** expanded to the environments the playbook targets (clinics, childcare, gyms, pet shops, F&B, etc.).

Three judgment calls worth your eye:

The playbook's spec table lists **66W**, but the pitch/USP copy repeatedly says **"15W — less than a light bulb."** Those conflict — I kept 66W (the spec table) on the site. You'll want to confirm the real figure.

The playbook leads with **"0.01μm — 30× finer than HEPA"** as its #1 talking point. I kept the more defensible "far smaller than PM2.5" wording on the public site rather than the HEPA comparison, and left ozone out entirely — same sales-lens caution you applied to the competitive slide before. Easy to switch to the playbook's exact line if you'd prefer it for the website.

Lastly, the playbook has two strong conversion assets the site doesn't use yet: the **14-day free trial** and **rental pricing** ($130/$120/$110 per unit on a 2-year, all-maintenance-included contract). The free trial in particular is a powerful CTA — I'd suggest featuring it. Want me to add a trial/pricing section and sync these details back into the handoff doc?

> _[file: qa_upd_full.png, not included in export]_

### Dom · 2026-06-03 09:40

also can you update the markdown file?

### Claude · 2026-06-03 09:41

Yes — let me sync the handoff doc with the confirmed AS-150 details. Let me view the relevant sections first.

> _tools used: view, str_replace_

Now let me view the conversion strategy and open-items sections to fold in the trial, pricing, and maintenance details.

> _tools used: view, str_replace_

The handoff doc is now synced with the playbook. Here's the updated file.

> _tools used: present_files_

Updated to match the page and the playbook. The changes:

- **AS-150 specs** now carry the full authoritative set (99.9% to 0.01μm, three-speed airflow and noise, dimensions, 71 plates, ionisation voltages, smart PM2.5 sensor, negative ions, the four SGS scopes).
- **Filtration** is the confirmed 5-layer system, no more placeholders.
- **USP bullets** match the page — including the smart sensor and the corrected "no filter *bills*" wording.
- New **§7.5 AS-150 commercial terms** — the rental pricing table ($130/$120/$110 per unit), the full list of what maintenance includes, the one-off purchase option, and the 14-day free trial.
- **Conversion strategy** now flags the free trial as a key secondary CTA.
- **Open items** cleaned up: the resolved ones (filtration stages, maintenance frequency) are gone, and the live decisions are now explicit — the 66W-vs-15W discrepancy, the HEPA-framing choice, and whether to publish pricing/trial on-site.

So the doc and the four HTML files are back in sync. The remaining open items are all genuine business decisions only you can make. When you're ready, the natural next steps are building the Airsonic and KOMC product pages (their reference specs and USP angles are already in §7) and deciding whether to add a pricing/trial section to the site.

### Dom · 2026-06-03 11:45

can you create a PDF fr the markdown file

### Claude · 2026-06-03 11:47

I'll convert the handoff doc to a PDF. Let me check the PDF skill first for the recommended approach.

> _tools used: view_

I'll render the markdown into a cleanly styled, branded PDF (rather than a plain one) by converting it to HTML with the QAS palette and printing to PDF.

> _tools used: bash_tool_

Let me QA the rendered PDF to make sure it looks clean.

> _tools used: bash_tool, view_

Clean and professional. Let me spot-check the page with the subscripts and pricing table to be safe.

> _tools used: bash_tool, view_

The PDF is ready — 6 pages, branded in the QAS palette, with styled tables, the pricing block, and clean typography (subscripts and units render correctly).

> _tools used: present_files_

Here's the handoff doc as a polished PDF — same content as the markdown, styled in your brand colours (navy headings, blue/cyan accents), with the colour-token and pricing tables formatted properly and a footer with page numbers. It's a clean thing to send a designer or attach to an email, sitting alongside the four HTML prototypes.

If you'd like, I can bundle everything — the four HTML files, the markdown, and this PDF — into a single zip for one easy handoff, or build the Airsonic and KOMC product pages so the full set of three is complete.

> _[file: qa_pdf-1.png, not included in export]_

> _[file: qa_pdf-2.png, not included in export]_

> _[file: qa_pdfb-5.png, not included in export]_

### Dom · 2026-06-03 12:14

```markdown
## 12. Open items to confirm
1. Single phone (8188 9998 vs 6665 1808) + email (sales@ vs accounts@) for sitewide use.
2. AS-150 power figure: spec table says **66W**, but pitch copy says **"15W"** — confirm which is correct (site currently shows 66W).
3. HEPA framing: playbook leads with "0.01μm — 30× finer than HEPA"; site uses the more defensible "far smaller than PM2.5" and omits ozone. Confirm preferred wording.
4. Whether to publish rental pricing and the 14-day trial on-site, or keep enquire-only.
5. Install lead time and enquiry response time.
6. Testimonials / client logos / before-after readings.
7. Any HIP-specific offer or eligibility angle.
8. Final logo asset + real product photography for Airsonic and KOMC.
```

1. use 81889998 + sales@qas.sg
2. Use 15W as the maintainance power
3. Follow the playbook
4. Dont publish pricing focus on 14 day trial or enquire
5. Install time is 1 hr & all enquries within the next day (But no need to mention this so much)
6. We will have all these content provided
7. No 
8. We will provide those much later

### Claude · 2026-06-03 12:19

All decisions noted. I'll roll them into the prototypes and the doc, then regenerate the PDF. Let me start with the sitewide phone/WhatsApp swap across all files.

> _tools used: bash_tool_

Now the product-page specifics — power figure (15W), HEPA framing, the 14-day trial CTAs, and removing HIP.

> _tools used: str_replace_

Now the homepage — remove the HIP tile and resolve the install-time placeholder (kept understated).

> _tools used: str_replace_

Now the contact page response-time placeholder:

> _tools used: str_replace_

Now let me update the handoff doc. First the phone/WhatsApp numbers, then I'll view it to apply the rest.

> _tools used: bash_tool, view_

Now the doc's remaining decisions — IA (drop HIP), HEPA framing, power, pricing-not-published, and the open-items list.

> _tools used: str_replace_

Finally, replace the open-items list with the locked decisions and what's still pending:

> _tools used: str_replace_

Now regenerate the PDF and QA the updated product page.

> _tools used: bash_tool, view_

All decisions are now baked into the prototypes and the doc, and the PDF is regenerated. Here's the full updated set.

> _tools used: present_files_

All eight decisions are in. Here's what changed across the set:

1. **Contact** — +65 8188 9998 and sales@qas.sg everywhere (WhatsApp links, footers, contact page).
2. **Power** — now ~15W typical in the spec table.
3. **HEPA** — the lead USP card now reads "Finer than HEPA… ~30× finer than the 0.3μm a HEPA filter targets," following the playbook; ozone stays off.
4. **Pricing** — kept off the site. The AS-150 page now leads with **"Start a 14-day free trial"** as the primary CTA (hero and closing band); pricing remains in the doc but is clearly marked internal-only.
5. **Install / response** — folded in lightly: "a quick install, usually within the hour" and "we usually reply within one business day."
6. **Testimonials** — placeholders left in place for the content you'll provide.
7. **HIP** — removed from the architecture, homepage tiles, and best-fit tags.
8. **Logo / Airsonic & KOMC photos** — current assets kept as placeholders; noted as coming later.

The handoff doc's section 12 is now a clean "Confirmed decisions" list plus a short "still to be provided by QAS," and the PDF reflects all of it.

The natural next step whenever you're ready is building the **Airsonic and KOMC product pages** — their specs and USP angles are already in the doc, so they'd follow the AS-150 template directly. Happy to do those, or to zip the whole set into one file for handoff.

> _[file: qa_prod_final.png, not included in export]_
