# Mary Ann Menes — Portfolio Launch & Leads Guide

A complete step-by-step guide to getting your portfolio live for free, capturing leads from your contact form, and everything else you need to turn it into a client-generating machine.

---

## PART 1: Adding Your Professional Photo

Before going live, replace the photo placeholder in your portfolio.

**What to do:**
1. Open `index.html` in a web browser (double-click the file)
2. In the hero card (top right), click the dashed circle with the camera icon
3. Select your professional headshot from your computer — it will appear instantly as a preview
4. The about section has a second placeholder — click and upload the same photo there

**Photo tips for best results:**
- Use a **clean, bright background** (white, soft gray, or a plain wall)
- Square crop ideally, or a close-up portrait orientation
- Minimum 400×400 pixels, ideally 800×800 or higher
- Wear something that matches the brand feel — neutrals, sage, or white work beautifully
- Smile — you want to look approachable and professional

> **Note:** The photo preview only works while the browser tab is open. To make it permanent, you need to add the photo directly into the HTML. See the instructions at the end of this section for how to do that.

**Making your photo permanent (one-time setup):**
1. Save your photo file as `photo.jpg` in the same folder as `index.html`
2. Open `index.html` in a text editor (Notepad on Windows, TextEdit on Mac)
3. Find the line: `<div class="photo-placeholder-inner" id="heroPlaceholderInner">`
4. **Above** that line, add: `<img src="photo.jpg" alt="Mary Ann Menes" style="width:120px;height:120px;border-radius:50%;object-fit:cover;margin:0 auto 1.25rem;">`
5. Save the file — your photo is now permanently embedded

---

## PART 2: Going Live for Free

You have two excellent free options. **Netlify Drop is the fastest** (30 seconds, no account needed). GitHub Pages is better for long-term management.

---

### Option A — Netlify Drop (Recommended · 30 seconds)

**Best for:** Getting live immediately with zero technical knowledge.

1. Go to **[netlify.com/drop](https://app.netlify.com/drop)** — no sign-up needed
2. Open your file manager and find the folder containing `index.html`
3. Drag the **entire folder** into the Netlify Drop box on the page
4. Netlify gives you a live URL instantly — something like `https://random-name-12345.netlify.app`
5. You can rename it to something like `https://maryannmenes.netlify.app` (free)

**To update your site later:**
- Create a free Netlify account (use the same email)
- Claim the site in your dashboard
- Drag and drop a new version of your folder whenever you make changes

**Cost:** Free forever (up to 100GB bandwidth/month — more than enough)

---

### Option B — GitHub Pages (Free · Good for long-term)

**Best for:** Keeping your site in version control with easy updates.

1. Create a free account at **[github.com](https://github.com)**
2. Click **New Repository** → name it `portfolio` → set it to **Public** → click Create
3. Click **uploading an existing file** → drag in your `index.html` → click **Commit changes**
4. Go to **Settings → Pages → Source** → select `main` branch → click **Save**
5. Your live URL will be: `https://yourusername.github.io/portfolio`

**Updating your site:** Just upload a new version of `index.html` to the same repository.

---

### Option C — Tiiny.host (Simplest of all)

1. Go to **[tiiny.host](https://tiiny.host)**
2. Upload your `index.html` file
3. Get a live URL in seconds — like `https://maryannmenes.tiiny.site`

**Free tier:** 5MB file limit, site expires after 14 days (paid plans are $5/month for permanent hosting)

---

## PART 3: Getting a Custom Domain (Optional but Recommended)

A custom domain like `maryannmenes.com` makes you look significantly more professional.

**Where to buy a domain:**
- **[Namecheap.com](https://namecheap.com)** — usually $10–15/year for a `.com`
- **[Porkbun.com](https://porkbun.com)** — often cheaper, good interface
- **[Google Domains](https://domains.google)** — simple, integrates well

**Recommended domain names for you:**
- `maryannmenes.com`
- `maryannva.com`
- `maryannmenes.pro`
- `executivevamaryann.com`

**Connecting your domain to Netlify (free):**
1. In Netlify dashboard → your site → **Domain settings** → **Add custom domain**
2. Enter your domain name and follow the steps
3. Netlify gives you nameserver addresses — copy them
4. Go to your domain registrar (e.g. Namecheap) → DNS settings → replace the nameservers with Netlify's
5. Wait 1–48 hours for it to propagate — then your domain is live
6. Enable **HTTPS** in Netlify (free SSL certificate) — one click

---

## PART 4: Making the Contact Form Actually Send You Emails

Right now the contact form shows a success message but doesn't send anything. Here's how to connect it to your real email — **for free.**

---

### Option A — Formspree (Easiest · Free up to 50 submissions/month)

1. Go to **[formspree.io](https://formspree.io)** and create a free account with your email
2. Click **+ New Form** → give it a name like "Portfolio Contact Form"
3. Formspree gives you a form endpoint URL like: `https://formspree.io/f/xabcdefg`
4. Open `index.html` in a text editor
5. Find this line: `<form id="contactForm" onsubmit="handleSubmit(event)">`
6. Replace it with: `<form id="contactForm" action="https://formspree.io/f/YOUR_CODE" method="POST">`
   (replace `YOUR_CODE` with your actual Formspree code)
7. Find the `handleSubmit` function in the `<script>` section and delete it (or leave it — Formspree handles submission)
8. Also find and delete `onsubmit="handleSubmit(event)"` from the form tag (if you kept it)

**What happens:** When someone fills out the form and clicks Send, Formspree emails you at the address you signed up with. The email contains all their details — name, email, service interested in, and message.

**Free plan includes:**
- 50 form submissions/month
- Email notifications to your inbox
- Basic spam filtering

**Upgrade to paid ($10/month) to get:**
- Unlimited submissions
- Email autoresponder (automatically reply to the person who submitted)
- Google Sheets integration (leads go directly into a spreadsheet)
- Custom success page redirect

---

### Option B — Netlify Forms (Best if you're using Netlify · Free up to 100/month)

If you're hosting on Netlify, you get form handling built in — no extra service needed.

1. Open `index.html` in a text editor
2. Find: `<form id="contactForm" onsubmit="handleSubmit(event)">`
3. Replace with: `<form id="contactForm" name="contact" method="POST" data-netlify="true">`
4. Add this inside the form (anywhere before the submit button):
   `<input type="hidden" name="form-name" value="contact" />`
5. Save, upload to Netlify
6. Go to Netlify dashboard → your site → **Forms** → you'll see all submissions there
7. Go to **Site settings → Forms → Form notifications** → add your email to get notified instantly

**Free plan includes:**
- 100 submissions/month
- Email notifications
- Spam filtering via Akismet

---

### Option C — EmailJS (No backend needed · Free 200 emails/month)

**Best for:** Keeping the existing form design exactly as-is.

1. Sign up at **[emailjs.com](https://emailjs.com)** (free)
2. Connect your Gmail or other email in **Email Services**
3. Create an **Email Template** — set it up with variables like `{{from_name}}`, `{{message}}`, `{{reply_to}}`
4. Get your **Service ID**, **Template ID**, and **Public Key** from the dashboard
5. Add this line just before your closing `</body>` tag in the HTML:
   ```html
   <script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@4/dist/email.min.js"></script>
   <script>emailjs.init("YOUR_PUBLIC_KEY");</script>
   ```
6. Update the `handleSubmit` function in your script to use EmailJS's `sendForm` method

(This option requires a little more technical comfort — consider Formspree first if you're new to this.)

---

## PART 5: What to Add to Your Portfolio Over Time

Your portfolio is a living document. Here's what will make it even more powerful:

### Add a Portfolio/Work Samples Section
This is the single most effective thing you can do to win clients. Add 3–5 samples such as:
- A screenshot of a workflow or automation you built in Zapier
- A Canva design or social media graphic you created
- A screenshot of a calendar or project management setup you organized
- A before/after of a process you improved
- Any property management reports or templates you've created (with sensitive info removed)

To add a portfolio section, let me know and I'll build it right into your HTML.

### Add Testimonials / Social Proof
Even one strong testimonial dramatically increases trust. Ask a past employer or client for a short quote. Add a section like:

> *"Mary Ann transformed how our executive calendar was managed. She's proactive, incredibly organized, and genuinely cares about getting things right."*
> — Previous Client, Real Estate Industry

### Add a Calendly Booking Link
Instead of waiting for email back-and-forth, let potential clients book a discovery call directly. It's free and removes friction.
1. Sign up at **[calendly.com](https://calendly.com)** (free)
2. Set up a 15- or 30-minute "Discovery Call" event
3. Add the link to your "Hire Me" button and in the contact section

### Add a Downloadable Resume
Put a download button in your hero or about section:
```html
<a href="MARY-ANN-MENES-RESUME.pdf" download class="btn-secondary">⬇ Download Resume</a>
```
Just place your resume PDF in the same folder as `index.html`.

---

## PART 6: Basic SEO (So People Can Find You on Google)

Your portfolio already has a meta description. Here's what else to do:

**1. Update the page title and description**
Open `index.html` and find these lines near the top. Make them specific:
```html
<title>Mary Ann Menes | Executive Virtual Assistant Philippines</title>
<meta name="description" content="Mary Ann Menes is a results-driven Executive VA offering calendar management, property operations, social media, and workflow automation. Available for remote work." />
```

**2. Add your location keywords naturally**
Clients searching for "Virtual Assistant Philippines" or "Executive VA remote" should find you. Your site already mentions this — keep it in.

**3. Submit to Google Search Console (free)**
1. Go to **[search.google.com/search-console](https://search.google.com/search-console)**
2. Add your live URL as a property
3. Submit your sitemap (just your URL + `sitemap.xml` — or just submit the homepage URL)
4. Google will index your site within a few days to a few weeks

**4. Add your portfolio URL everywhere:**
- LinkedIn profile (website field)
- Email signature
- Upwork / OnlineJobs.ph / Fiverr profiles
- Your resume PDF (replace the Google Sites link)

---

## PART 7: Where to Share Your Portfolio to Get Clients

Now that your site is live, share it in these places:

**Job Platforms for VAs:**
- **Upwork** — upwork.com (largest freelance marketplace)
- **OnlineJobs.ph** — onlinejobs.ph (Philippine VA-focused, many US clients)
- **Fiverr** — fiverr.com (good for offering specific packages)
- **Belay Solutions** — for high-level executive VA roles
- **Time Etc** — timeete.com

**LinkedIn:**
- Update your LinkedIn headline to include "Virtual Executive Assistant | Open to Work"
- Add your portfolio URL in the "Website" field of your profile
- Post once a week — share a tip about VA work, productivity, or property management. This builds authority and attracts inbound leads.

**Facebook Groups:**
- "Virtual Assistant Philippines" groups
- "Work from Home Philippines"
- "Real Estate Virtual Assistants"

**Your Email Signature:**
Add your portfolio link to every email you send:
```
Mary Ann Menes
Executive VA | Creative Support | Property Manager
Portfolio: https://maryannmenes.netlify.app
LinkedIn: linkedin.com/in/mary-ann-menes
```

---

## PART 8: Quick Launch Checklist

Before you share your link with anyone, tick off these items:

- [ ] Added professional photo to hero and about sections
- [ ] Portfolio is live at a public URL (Netlify, GitHub Pages, etc.)
- [ ] Contact form is connected to real email (Formspree or Netlify Forms)
- [ ] Tested the contact form — sent a test message to yourself
- [ ] Updated LinkedIn with your new portfolio URL
- [ ] Updated your resume PDF with the new portfolio URL
- [ ] Added portfolio URL to your email signature
- [ ] Tested on mobile — everything looks good on your phone

---

## Summary: Fastest Path to Live in 10 Minutes

1. Go to **netlify.com/drop** — drag your folder in — get a URL (2 min)
2. Go to **formspree.io** — create a form — update the form `action` in your HTML — re-upload (5 min)
3. Update your LinkedIn with the new link (1 min)
4. Send a test message through your contact form to confirm emails arrive (2 min)

You're live. 🎉

---

*Generated with Claude AI · Last updated May 2026*
