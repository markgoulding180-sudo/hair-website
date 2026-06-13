# Hair, Nails & Beauty by Anne Rusz — Website

## What's included
- `index.html` – full one-page site (hero, services/prices, Crown Revival hair systems, gallery placeholders, about, reviews, booking form, map, footer)
- `robots.txt` and `sitemap.xml` – for search engine crawling
- Built-in **JSON-LD structured data** (LocalBusiness/HairSalon + FAQPage) for Google rich results & Maps
- Booking form wired to **Supabase** (you just add your project URL + anon key)

## 1. Replace placeholder details
- Swap out the colour-block gallery images for real photos (filenames can stay the same class `.ph`, or replace `<div class="ph">` with `<img src="...">`)
- Update `og:image` URL once you have a real cover photo
- Double-check phone/email/address are correct everywhere (they appear in 4 places: header isn't shown, but footer, booking info, JSON-LD, and meta tags)

## 2. Supabase setup
1. Create a project at supabase.com
2. Create a table `bookings` with columns:
   - `id` (uuid, primary key, default gen_random_uuid())
   - `name` (text)
   - `phone` (text)
   - `email` (text)
   - `service` (text)
   - `location` (text)
   - `appointment_date` (date)
   - `appointment_time` (time)
   - `notes` (text)
   - `created_at` (timestamptz, default now())
3. Enable Row Level Security, then add a policy allowing `INSERT` for the `anon` role only (no SELECT/UPDATE/DELETE for anon).
4. In `index.html`, find `SUPABASE_URL` and `SUPABASE_ANON_KEY` near the bottom of the file and paste in your project's values (Project Settings → API).

## 3. Deploy to Vercel
1. Push this folder to a GitHub repo (or drag-and-drop deploy on vercel.com)
2. Import the repo in Vercel — no build step needed, it's static HTML
3. Set your custom domain (e.g. hairnailsbeautybyannerusz.co.uk) in Vercel project settings
4. Update the `canonical`, `og:url`, `og:image`, sitemap `<loc>`, and JSON-LD `url`/`@id` fields in `index.html` to match your real domain

## 4. Ranking in Google Maps (Local SEO checklist)
This site gives you the on-page foundation, but ranking in the **Maps "top 3" pack** depends heavily on signals outside the website too:

1. **Google Business Profile** (essential)
   - Claim/verify your business at business.google.com using the exact same name, address & phone (NAP) as the website
   - Choose categories: "Hair salon", "Beauty salon", "Massage therapist" etc.
   - Add your service area (Draycott, Long Eaton, Borrowash, etc.)
   - Upload real photos regularly, post updates/offers weekly
   - Add your booking link and website link

2. **Consistent NAP** — make sure your name/address/phone are written identically everywhere (website, Google, Facebook, Instagram, any directories)

3. **Reviews** — actively ask happy clients for Google reviews; reply to every review. Review count & recency are major Maps ranking factors

4. **Citations/directories** — list the business on Bing Places, Yell, Facebook, Checkatrade/Treatwell if relevant, etc., all with matching NAP

5. **Local content** — the site already targets "mobile hairdresser Draycott", "home salon Derbyshire" etc. Consider adding a blog/news section over time with local-area posts (e.g. "Mobile Hairdresser for Long Eaton Brides")

6. **Speed & mobile-friendliness** — this site is lightweight, mobile-first, and uses semantic HTML, which helps Core Web Vitals

7. **Backlinks** — get listed/linked from local community sites, Facebook group, supplier sites (e.g. Crown Revival's own salon directory if available)

None of the above guarantees a top-3 Maps position (competition and Google's algorithm both matter), but together with this site they give you the strongest realistic foundation.
