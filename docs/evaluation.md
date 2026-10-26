# Website Redesign Evaluation: mgeom.cz

**Client:** MGeom s.r.o. (Miroslav Marinčič, jednatel)
**Website:** https://www.mgeom.cz/ (Webflow, "Constructor X" template)
**Business type:** Land surveying (geodet), Praha 10 – Kolovraty
**Date:** 25 Oct 2026

**Overall score: 2.3 / 5** (average of steps 3–9). The business content is real and the photos are good. The site still loses enquiries to template leftovers, a broken phone link and a near-empty Google listing.

New build = `mgeom.html` in this folder, checked the same day.

---

## 1. Understand the business first

Not asked yet. Confirm these with the client. The likely answers are in brackets.

- [ ] **Main action:** (request a quote, or call)
- [ ] **How customers find them:** (Google, recommendations from architects and builders, municipalities)
- [ ] **What people keep asking:** (price, how soon you can come, do you cover my area, what documents I need)
- [ ] **What earns the most:** (geometric plans, staking out, surveys for design work?)

## 2. Measure the old site before you change it

| Metric | Before | 30 days | 90 days |
| --- | --- | --- | --- |
| PageSpeed mobile: performance / accessibility / best practices / SEO | 85 / 91 / 100 / 100 | | |
| Largest Contentful Paint (mobile) | 3.7 s | | |
| Google position for "geodet Praha 10" | not in the top 10 | | |
| Google Business Profile | exists; 0 reviews, no hours, category "Geotechnické inženýrství" | | |
| Enquiries or calls per month | ask client | | |

## 3. Run the 5-second test on a phone

Score: **3 / 5**

- [x] What this place is: "Měříme s přesností…" plus a real surveyor in the hero
- [ ] Where it is: the address only appears below the hero
- [ ] When it's open: no opening hours anywhere
- [x] How to contact or book: "Poptat cenu" button in the header (the phone number isn't visible above the fold)

## 4. Check the 3–5 tasks customers come for

Score: **2 / 5**

| This client's task | Now | Notes |
| --- | --- | --- |
| Find the right service | Partly works | All 6 services are listed, but the services slider stacks every card in one 4,659 px column |
| Get an idea of price and timing | Missing | No "from" prices, no typical turnaround |
| Check the area they cover | Missing | Only the head-office address is shown |
| Request a quote | Works, with issues | The form's success and error messages are in English, and the "príjmení" label has a typo |

## 5. Look at trust and friction

Score: **2 / 5**

- [x] Real photos and a real face (the director in the field)
- [x] 2 real projects (Řepy public lighting, Poniklá family house)
- [ ] **No reviews or references.** Competitors in the Google map pack show 4–19 reviews each.
- [ ] No prices
- [ ] **The footer phone link dials a US template number, (323) 238-0682**, while the text shows +420 605 551 059
- [ ] No stated response time

## 6. Make sure local search can find them

Score: **2 / 5**

- [ ] Google Business Profile: it exists, but shows "Vlastníte tuto firmu?" (it looks unclaimed), has no hours, no reviews, and the category is geotechnical engineering, not "Zeměměřič"
- [x] Name, address and phone are the same on the site, in the Google listing and in the business register
- [ ] The title "MGeom s.r.o. - geodetické služby" has no city. Add "Praha".
- [ ] No LocalBusiness schema
- [ ] The page language is set to `lang="en"` on a Czech site
- [ ] English version: probably not needed for this audience

## 7. Check the content

Score: **2 / 5**

- [ ] Template leftovers in the menu: "Shop CMS", "Blog CMS", "Style Guide", "Browse More Templates", plus a Malibu building project and a home colour palette blog post
- [ ] Image alt text reads "… - Constructor X Webflow Template"
- [ ] Mixed languages: "Get a quote" next to "Poptat cenu"
- [x] The service descriptions are specific and use the words customers use (geometrický plán, vytyčení)

## 8. Speed and accessibility

Score: **3 / 5**

- [x] 18 px body text; accessibility score 91
- [ ] LCP of 3.7 s on mobile (the target is under 2.5 s)
- [ ] Images could be about 452 KiB smaller (WebP, correct sizes)
- [ ] Render-blocking Webflow CSS/JS costs about 1.9 s

## 9. Legal basics

Score: **2 / 5**

- [x] Trader's details in the footer: MGeom s.r.o., IČO 22653449, Do Lipan 477/20, Praha 10
- [ ] No privacy policy
- [ ] The contact form has no GDPR or data-processing information
- [ ] Cookie banner: not needed unless analytics are added

## 10. Plan how the site gets updated

- [ ] What changes: new projects a few times a year, occasionally a service. Offer a care plan, or Pages CMS for the projects.
- [ ] Hand over the repo or a zip plus a one-page guide

## 11. Measure again after launch

- [ ] Recheck the step 2 numbers at 30 and 90 days
- [ ] Send the client a before/after report

---

## How far the new build (`mgeom.html`) already gets

| Issue | New build |
| --- | --- |
| Template leftovers and English text | Fixed |
| Footer phone link | Fixed (one correct `tel:` link) |
| Page language | Fixed (`lang="cs"`) |
| Services slider stacking | Fixed |
| Trader's details (IČO) | Kept |
| Meta description | **Missing.** The live site has one, so add it back. |
| LocalBusiness schema | Missing |
| Opening hours | Missing |
| Quote form | Missing (mailto only). Decide: Formspree plus a GDPR note, or keep email and phone |
| Privacy policy | Missing |
| Reviews or references | Missing |
| Images | 18 still hotlinked from Webflow's CDN; download and compress them |

## Top 3 fixes for this client

1. **Fix what blocks contact.** The phone link and the template and English leftovers go away with the new build. Add a Czech quote form with a GDPR note, or keep a clear phone-first CTA.
2. **Fix the Google Business Profile.** Claim it, set the category to "Zeměměřič", add hours and service area, and ask 5–10 past clients (architects, builders, municipalities) for reviews. This is where local customers compare surveyors.
3. **Answer the quote questions on the site.** Say which area they cover, typical turnaround, and "from" prices or what drives the price. Then add "Praha" to the title, write a meta description and add LocalBusiness schema.
