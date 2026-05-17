# Sanjeevani Multispeciality Hospital — PRD

## Problem Statement
Build a complete, production-ready single-page hospital website for Sanjeevani Multispeciality Hospital, Sumerpur, Pali, Rajasthan. Single HTML file with embedded CSS + JS, using Google Fonts and qrcode.js CDN. Mobile-first, responsive, with multi-step booking form, QR code, FAQ accordion, animated counters, floating WhatsApp/Emergency buttons.

## Architecture
- Single static HTML at `/app/frontend/public/index.html` served via CRA dev server (port 3000)
- `/app/frontend/src/App.js` returns `null` so the React bundle does not override static content
- localStorage stores bookings (`sh_bookings`) and contact messages (`sh_messages`)
- CSS variables namespaced as `--sh-*` to avoid conflicts with shadcn theme vars in `src/index.css`

## Implemented (2025-12)
- Sticky header with top emergency bar, hamburger mobile menu, smooth-scroll nav
- Hero with blue gradient, dual CTA, 4 trust badges
- Why Choose Us (6 cards), Services (11 cards)
- Red Emergency banner with phone numbers and directions link
- Booking promo (3-step graphic + benefits)
- Doctors preview (4 cards) and Full doctors grid (10 doctors w/ CSS avatars)
- Testimonials (3 cards + star rating)
- About section with animated counters (40+, 50+, 5+, 3.8/5), values, facilities, founder message
- Departments (10 cards) with services, doctor, fee, "Book Now" preselect
- Multi-step booking form (5 steps + progress indicator):
  - Step 1: Department + Doctor cascading dropdowns + fee
  - Step 2: Date picker (today→+30d) + time slot grid with random "booked" slots
  - Step 3: Patient details with validation (name, age, gender, 10-digit phone, email, reason)
  - Step 4: Payment (Pay at Hospital / Pay Online with UPI IDs + QR placeholder)
  - Step 5: Animated success with Booking ID (SH+date+3 digits), summary card, action buttons
- Bed Availability (4 cards: ICU, Ward, Private, NICU)
- QR Scanner section with REAL QR code (qrcodejs CDN) + Download as PNG
- Contact (info + form with validation + Google Maps iframe + social icons)
- FAQ accordion (8 Q&A) with smooth open/close
- Floating WhatsApp (bottom-right, green) + Emergency (bottom-left, red, pulsing)
- Footer (4 columns)
- Toast notifications

## Next Action Items
- Optional: connect contact form to backend / email service (currently localStorage)
- Optional: backend persistence for bookings + admin dashboard
- Optional: actual payment gateway (Razorpay/Stripe) for online consultation fee
