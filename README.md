# From Stage to Scale

Single-page website for the 2-day speaker program in Miami Beach.

Domain: fromstagetoscale.com

## Design
- Minimal, premium, mobile-first
- Dark navy background (#0A0F1C) with warm gold accent (#D4A373)
- Large readable type (Playfair Display + Inter)
- Smooth scroll and fade-in animations
- Few clicks to buy

## Sections
All requested sections are included in order, with clear placeholders for:
- Dates, venue, early-bird price, deadline, refund policy
- Coach photos (styled placeholders with initials)

No invented testimonials, reviews, logos, or statistics.

## Lead Capture
"Get the Free Guide" opens a modal form (name, email, phone) for "The 4-Step Speech Preparation Method".

Currently logs to console and shows success. To save to a database:

1. Create a backend endpoint (Vercel serverless function recommended)
2. Replace the TODO in the form submit handler with a `fetch('/api/leads', ...)`
3. Options: Supabase, Vercel KV/Postgres, Google Sheets via Apps Script, or Formspree

## Checkout & Seats
"Reserve Your Seat" buttons scroll to pricing and trigger `startCheckout()`.

Currently shows an alert. To take payment:

1. Set up Stripe (create a product for the $2,500 seat)
2. Build a serverless function that:
   - Checks remaining seats (max 15)
   - Creates a Stripe Checkout Session
   - Returns the session URL
3. Redirect the user to that URL
4. On successful webhook, decrement seat count

Alternatively, use a Stripe Payment Link and manage the 15-seat limit manually or with a simple counter.

Early-bird pricing can be handled with Stripe coupons or a second product/price.

## Deployment
This is a static site. Deploy to Vercel, Netlify, or any host. Point fromstagetoscale.com to it.

## Next Steps
- Replace placeholders with real dates, venue, prices, and policy
- Add real coach photos
- Connect lead form to a database
- Connect Stripe Checkout with seat tracking
- Test on mobile

Copy is plain, short sentences that speak directly to the reader as "you".
