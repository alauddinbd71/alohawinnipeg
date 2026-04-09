# ALOHA PLUMBING — COMPLETE WEBSITE SYSTEM
## WordPress Deployment Guide + File Reference

---

## 📁 FILES INCLUDED

| File | Page | Purpose |
|------|------|---------|
| `index.html` | Homepage | Main lead generation page — all services, trust, CTA |
| `emergency-plumber.html` | Emergency Page | Highest-intent emergency traffic |
| `pipe-relining.html` | Pipe Relining | Highest-revenue service — CIPP trenchless |
| `drain-cleaning.html` | Drain Cleaning | High-volume service page |
| `lp-emergency-call.html` | Google Ads LP | Dedicated landing page — call-only, no nav |
| `WORDPRESS-GUIDE.md` | This file | Deployment instructions |

---

## 🚀 STEP-BY-STEP WORDPRESS DEPLOYMENT

### PHASE 1 — HOSTING SETUP (Day 1 Morning)

1. **Keep existing domain**: alohawinnipeg.ca (already registered)
2. **Hosting**: Sign up at SiteGround Business plan (~$3.99/mo intro)
   - Choose Canada server location
   - Select "WordPress" during setup wizard
3. **Install WordPress**: Use SiteGround's 1-Click WordPress installer
4. **SSL Certificate**: Enable free Let's Encrypt SSL (SiteGround does this automatically)

---

### PHASE 2 — THEME SETUP (Day 1 Midday)

**Recommended Theme: Kadence (FREE)**

1. WordPress Dashboard → Appearance → Themes → Add New
2. Search "Kadence" → Install → Activate
3. Go to: Appearance → Kadence → Starter Templates
4. Search "Plumber" or "HVAC" starter template
5. Click "Import Complete Site"
6. This gives you the structure — you'll replace content with the copy from these HTML files

**Alternative**: Astra Theme (also free, similar approach)

---

### PHASE 3 — REQUIRED PLUGINS (Day 1 Afternoon)

Install these via: Dashboard → Plugins → Add New

| Plugin | Purpose | Free? |
|--------|---------|-------|
| Rank Math SEO | SEO, schema, sitemap, local business | Free |
| WP Rocket | Speed optimization (caching) | Paid $49/yr — WORTH IT |
| ShortPixel | Image compression | Free up to 100 images/mo |
| Wordfence | Security firewall | Free |
| Widget for Google Reviews | Show 4.9★ feed live | Free |
| WPForms Lite | Contact forms | Free |
| Insert Headers and Footers | Google Tag Manager install | Free |

**Call Tracking**:
- Sign up at callrail.com (~$45 CAD/mo)
- Get 3 tracking numbers: Google Ads, Organic, Direct
- Install CallRail WordPress plugin

---

### PHASE 4 — PAGE CREATION (Day 1 Afternoon)

**Method A — Use the HTML files as reference (Recommended)**

For each page in WordPress:
1. Dashboard → Pages → Add New
2. Use Kadence Blocks or Elementor to recreate the layout
3. Copy the exact headlines, copy, and CTAs from the HTML files
4. Add your actual photos (team, work photos) where placeholders are

**Method B — Direct HTML paste**

1. In page editor, switch to "Code Editor" mode (top right: three dots → Code editor)
2. Paste the full HTML from each file
3. This works but loses WordPress styling benefits

**Pages to Create (in order of priority)**:

1. **Homepage** (set as Front Page in Settings → Reading)
2. **Emergency Plumber** → URL: /emergency-plumber
3. **Pipe Relining** → URL: /pipe-relining
4. **Drain Cleaning** → URL: /drain-cleaning
5. **Sewer Repair** → URL: /sewer-repair (create based on emergency page style)
6. **Camera Inspection** → URL: /camera-inspection
7. **About** → URL: /about
8. **Contact** → URL: /contact
9. **Areas Served** → URL: /areas-served
10. **Buying a Home** → URL: /buying-a-home

**Landing Page (Google Ads)**:
- Create page → URL: /lp/emergency-call
- Use lp-emergency-call.html as template
- **IMPORTANT**: In page settings, select template "Blank Canvas" or "No Header/Footer"
  - This removes navigation so visitors can only call

---

### PHASE 5 — SEO SETUP WITH RANK MATH

After installing Rank Math:

**Local Business Schema** (Critical for local SEO):
1. Rank Math → Titles & Meta → Local SEO
2. Fill in:
   - Business Name: Aloha Plumbing & Drain Services Inc.
   - Type: Plumber
   - Phone: +1 (204) 890-7725
   - Address: Unit B - 40 Caithness Rd., Winnipeg, MB R3H 0V4
   - Service Area: Winnipeg, Selkirk, St. Andrews, Brandon, Manitoba
   - Hours: (enter your actual hours)

**Sitemap**:
1. Rank Math → Sitemap Settings → Enable
2. Submit sitemap URL to Google Search Console: yoursite.ca/sitemap.xml

**Per-Page SEO** (for each page):
- Edit page → Rank Math meta box at bottom
- Set: Focus keyword, meta title, meta description
- Target score: 80+

Example for Homepage:
- Focus Keyword: "plumber Winnipeg"
- Title: "Aloha Plumbing Winnipeg | Emergency Plumber | (204) 890-7725"
- Description: "Winnipeg's #1 emergency plumber. Same-day service, free camera inspection, Canada's only Double Master Certified pipe reliner. Call (204) 890-7725."

---

### PHASE 6 — MOBILE OPTIMIZATION

**Sticky Call Button** (most important mobile element):

Add this to your theme's footer or via "Insert Headers and Footers" plugin:

```html
<!-- Sticky mobile call button -->
<div id="mobile-call-bar" style="display:none;position:fixed;bottom:0;left:0;right:0;z-index:9999;background:#D93025;padding:14px 20px;text-align:center;">
  <a href="tel:+12048907725" style="color:#fff;font-family:'Bebas Neue',sans-serif;font-size:22px;letter-spacing:1px;display:flex;align-items:center;justify-content:center;gap:10px;text-decoration:none;">
    📞 CALL NOW — (204) 890-7725
  </a>
</div>
<script>
  if(window.innerWidth <= 768){
    document.getElementById('mobile-call-bar').style.display = 'block';
    document.body.style.paddingBottom = '58px';
  }
</script>
```

**Mobile Speed Rules**:
- No hero videos on mobile (use static image instead)
- Font size minimum 16px (prevents iOS zoom)
- All buttons minimum 48px height
- Phone number must be tap-to-call: `<a href="tel:+12048907725">`

---

### PHASE 7 — SPEED OPTIMIZATION

**Target**: LCP under 2.5 seconds on mobile (Google PageSpeed Insights)

With WP Rocket:
1. Enable Page Caching
2. Enable Browser Caching
3. Enable Minify CSS & JS
4. Enable LazyLoad for images
5. Preload critical CSS

**Images**:
- Compress all images before uploading (use ShortPixel or TinyPNG.com)
- Use WebP format when possible
- Add alt text to every image (important for SEO)

**Check your speed**:
- pagespeed.web.dev (test mobile score — target 80+)
- gtmetrix.com (detailed breakdown)

---

### PHASE 8 — GOOGLE ANALYTICS + TRACKING

1. **Google Analytics 4**: analytics.google.com → Create property
2. **Google Tag Manager**: tagmanager.google.com → Create account
3. Install GTM code via "Insert Headers and Footers" plugin
4. In GTM, add:
   - GA4 Configuration tag
   - Phone call click tracking (track clicks on tel: links)
   - Form submission events

**Google Search Console**:
1. search.google.com/search-console
2. Add property → verify via HTML tag
3. Submit sitemap

---

## 🎯 GOOGLE ADS SETUP (Day 2)

### Campaign Structure

**Campaign 1: Emergency Plumbing**
- Budget: $20/day CAD
- Keywords (Broad Match Modified):
  - "emergency plumber winnipeg"
  - "plumber near me winnipeg"
  - "sewer backup winnipeg"
  - "burst pipe winnipeg"
  - "plumber open now winnipeg"
- Landing page: /lp/emergency-call

**Campaign 2: Drain Cleaning**
- Budget: $15/day CAD
- Keywords:
  - "drain cleaning winnipeg"
  - "blocked drain winnipeg"
  - "clogged sewer line winnipeg"
  - "root drain clearing winnipeg"
- Landing page: /drain-cleaning

**Campaign 3: Pipe Relining**
- Budget: $10/day CAD
- Keywords:
  - "pipe relining winnipeg"
  - "trenchless pipe repair winnipeg"
  - "sewer pipe relining cost"
  - "no dig pipe repair winnipeg"
- Landing page: /pipe-relining

### Ad Copy (RSA Headlines — use 15)
1. Winnipeg Plumber — Call Now
2. Same-Day Drain Cleaning
3. Sewer Backup? We're Coming
4. No-Dig Pipe Repair Experts
5. ★ 4.9 Rated · 92 Reviews
6. Free Camera Inspection
7. Licensed Winnipeg Plumbers
8. Root Clearing Specialists
9. Skip the $10,000 Excavation
10. Only Certified Reliner in Canada
11. Available Today · Flat Pricing
12. Basement Backup Fixed Fast
13. (204) 890-7725 · Call Now
14. Second Opinion — Save Thousands
15. Canada's Most Certified Plumber

### Ad Descriptions (use 4)
1. "Sewer backup or blocked drain? Aloha responds fast — same-day service, camera inspection included. Call (204) 890-7725."
2. "4.9 stars from 92 Winnipeg homeowners. Flat-rate pricing, no hidden fees. Canada's only Double Master Certified pipe reliner."
3. "We fixed what others couldn't. Customers save $2,000–$13,000 vs competitor quotes. Free camera inspection. Call now."
4. "Licensed in Winnipeg, Selkirk & Brandon. Same-day emergency service. Tap to call — (204) 890-7725."

### Extensions (All Required)
- **Call Extension**: +1 (204) 890-7725
- **Location Extension**: Link Google My Business
- **Sitelinks**: Emergency Service | Free Camera Inspection | Pipe Relining | Read Reviews
- **Callouts**: 4.9 Stars | Same-Day Service | Flat-Rate Pricing | No-Dig Pipe Repair
- **Structured Snippet**: Services: Drain Cleaning, Pipe Relining, Sewer Repair, Emergency Plumbing

### Settings
- Geo-targeting: Winnipeg city + 25km radius
- Ad schedule: 7AM–9PM (adjust after 2 weeks)
- Bidding: Maximize Clicks (weeks 1-2) → Maximize Conversions
- Device bid adjustment: +20% mobile

### Negative Keywords (Add from Day 1)
- free, DIY, how to, tutorial, school, course, certification, salary, jobs, career, employment, plumbing school, become a plumber, youtube

---

## 📋 48-HOUR LAUNCH CHECKLIST

### Day 1 — Website
- [ ] WordPress installed on alohawinnipeg.ca
- [ ] Kadence theme installed + starter template imported
- [ ] 7 plugins installed and configured
- [ ] Homepage created with all sections
- [ ] Emergency plumber page live
- [ ] Pipe relining page live
- [ ] Drain cleaning page live
- [ ] Google Ads landing page live (/lp/emergency-call)
- [ ] Contact page live with phone + form
- [ ] Sticky mobile call button working
- [ ] All phone numbers are tap-to-call links
- [ ] Rank Math configured: local schema, sitemap
- [ ] Google Search Console: site verified, sitemap submitted
- [ ] Google Analytics 4 connected
- [ ] PageSpeed mobile score: 75+
- [ ] Test on actual iPhone (not just browser emulation)

### Day 2 — Google Ads
- [ ] Google Ads account created or accessed
- [ ] Conversion tracking: call clicks + form submissions
- [ ] CallRail numbers installed for: ads, organic, direct
- [ ] Campaign 1: Emergency Plumbing — live
- [ ] Campaign 2: Drain Cleaning — live
- [ ] Campaign 3: Pipe Relining — live
- [ ] All ad extensions added
- [ ] Negative keyword list added
- [ ] Daily budget caps set
- [ ] Geo-targeting confirmed: Winnipeg area only
- [ ] Google My Business: link to ads account

### Week 2 Actions
- [ ] Create sewer repair page
- [ ] Create camera inspection page
- [ ] Create about page
- [ ] Create areas served page
- [ ] Create buying a home page
- [ ] Set up review request system (text after job)
- [ ] Add Google Reviews widget to homepage
- [ ] Check Google Ads: which keywords are converting?

---

## 🎨 BRAND COLORS (for WordPress Customizer)

| Use | Color | Hex |
|-----|-------|-----|
| Primary/CTAs | Emergency Red | #D93025 |
| Dark Red (hover) | Red Dark | #B71C1C |
| Background Dark | Navy | #0D1B2A |
| Trust/Accent | Gold | #F5A623 |
| Light Background | Off White | #F8F6F2 |
| Body Text | Near Black | #1A1A1A |

## 🔤 FONTS
- Display/Headlines: Bebas Neue (Google Fonts — free)
- Serif Accents: DM Serif Display (Google Fonts — free)  
- Body: DM Sans (Google Fonts — free)

Add to WordPress Customizer → Additional CSS:
```css
@import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Sans:wght@300;400;500;600&family=DM+Serif+Display&display=swap');
```

---

## 📞 KEY BUSINESS INFO (Use Everywhere)

- **Business Name**: Aloha Plumbing & Drain Services Inc.
- **Phone**: (204) 890-7725 / +1 204-890-7725
- **Text**: Same number — mention "call or text"
- **Address**: Unit B – 40 Caithness Rd., Winnipeg, MB R3H 0V4
- **Website**: alohawinnipeg.ca
- **Google Rating**: 4.9 ★ (92 reviews)
- **Key Differentiator**: Canada's ONLY Double Master Certified Pipe Reliner
- **Service Area**: Winnipeg, Selkirk, St. Andrews, Brandon, MB

---

## 💡 CONTENT WRITING NOTES

When creating additional pages, always include:

1. **The certification claim**: "Canada's only Double Master Certified pipe reliner"
2. **The savings angle**: Customers save $2,000–$13,000 vs. competitors
3. **The camera inspection**: Free, included, live footage
4. **Named technicians**: Brett, Julian, John, Presley — use names to build trust
5. **Reviews**: Use the real reviews from Google — they are GOLD
6. **Flat-rate pricing**: Multiple reviews confirm this — use it as a differentiator vs. Mr. Rooter

**NEVER**: 
- Use "cheap" (use "competitive" or "fair")
- Promise 24/7 without confirming current hours
- Make claims you can't back up

---

*Generated for: Aloha Plumbing & Drain Services Inc. · Winnipeg, MB*
*System created: 2025*
