# Wedding Website Setup Guide

## 🎨 Logo Generation Prompt

Use this prompt with your AI image generator (MidJourney, DALL-E, Stable Diffusion, etc.):

**Prompt:**
```
Create an elegant wedding logo featuring intertwined initials "F" and "Z" in a luxurious style. The design should incorporate:
- Ornate Mughal-inspired geometric patterns
- Gold and beige color palette (#D4AF37 gold, #F5F0E8 beige)
- Subtle floral motifs (roses or jasmine)
- Art deco elements with South Asian influences
- Elegant serif typography
- Symmetrical composition with decorative flourishes
- Suitable for both digital and print use
- Clean, sophisticated, and timeless design
- Can include subtle wedding rings or heart symbolism

Style: Luxury wedding invitation, elegant, ornate but not overwhelming, balanced composition, high-end feel, suitable for both traditional and modern aesthetics. Think: upscale Indian/Pakistani wedding invitation meets contemporary luxury branding.

Format: Square logo, transparent background, high resolution, suitable for use on beige/cream backgrounds.
```

**Alternative simpler prompt:**
```
Minimalist luxury wedding monogram logo with letters F and Z, gold foil effect, ornate decorative frame, Mughal architecture inspired patterns, elegant serif font, beige and gold colors, symmetrical design, suitable for South Asian wedding
```

---

## 📊 Google Sheets Setup

### Step 1: Share Your Sheet
1. Open your Google Sheet: https://docs.google.com/spreadsheets/d/1G7OKh0NmmLdOj9fzUqY9ogg4DCmdwEW1yYHBezlqzuQ/edit
2. Click "Share" button (top right)
3. Change "Restricted" to "Anyone with the link"
4. Set permission to "Viewer"
5. Click "Done"

### Step 2: Sheet Structure

**Your sheet should have these columns (Column A through R):**

| Column | Field Name | Example Data |
|--------|------------|--------------|
| A | groom_name_en | Mohammad Faizan |
| B | groom_name_ur | محمد فیضان |
| C | bride_name_en | Zeba Khan |
| D | bride_name_ur | زیبا خان |
| E | baraat_date | 2026-03-29 |
| F | baraat_time | 7:00 PM |
| G | baraat_venue_en | Delite Gardens, Surajkund |
| H | baraat_venue_ur | ڈیلائٹ گارڈنز، سورج کنڈ |
| I | baraat_map_url | https://maps.app.goo.gl/mvU2UimRHpoKVmwt8 |
| J | reception_date | 2026-03-30 |
| K | reception_time | 7:00 PM |
| L | reception_venue_en | Garden of Five Senses |
| M | reception_venue_ur | گارڈن آف فائیو سینسز |
| N | reception_map_url | https://maps.app.goo.gl/q2m6U4dyppnzsLKH9 |
| O | contact1_name | Haji Mohammad Mustafa |
| P | contact1_phone | 919650944281 |
| Q | contact2_name | Mohammad Arshad |
| R | contact2_phone | 919650944281 |

### Step 3: Copy-Paste Ready Data

**Copy this entire row and paste it into Row 1 of your sheet (starting from A1):**

```
Mohammad Faizan	محمد فیضان	Zeba Khan	زیبا خان	2026-03-29	7:00 PM	Delite Gardens, Surajkund	ڈیلائٹ گارڈنز، سورج کنڈ	https://maps.app.goo.gl/mvU2UimRHpoKVmwt8	2026-03-30	7:00 PM	Garden of Five Senses	گارڈن آف فائیو سینسز	https://maps.app.goo.gl/q2m6U4dyppnzsLKH9	Haji Mohammad Mustafa	919650944281	Mohammad Arshad	919650944281
```

**Note:** The data above is TAB-separated. When you paste it into Google Sheets, it will automatically go into separate columns.

### Step 4: Urdu Text Translation Help

For the Urdu translations, here are the venue names in Urdu:
- **Delite Gardens, Surajkund:** ڈیلائٹ گارڈنز، سورج کنڈ
- **Garden of Five Senses:** گارڈن آف فائیو سینسز

You can use Google Translate for other Urdu text if needed.

---

## 🖼️ Adding Your Logo to the Website

Once you have your logo generated:

1. **Upload your logo to an image hosting service:**
   - Use [ImgBB](https://imgbb.com/) (free, no account needed)
   - Or [Imgur](https://imgur.com/)
   - Upload your logo and get the direct image URL

2. **Update the website HTML:**
   - Find this line in the HTML (around line 10):
     ```html
     <meta property="og:image" content="https://i.ibb.co/placeholder-wedding.jpg">
     ```
   - Replace `https://i.ibb.co/placeholder-wedding.jpg` with your actual logo URL
   
   - Also update line 13:
     ```html
     <meta name="twitter:image" content="https://i.ibb.co/placeholder-wedding.jpg">
     ```

3. **Replace the emoji placeholder:**
   - Find this section (around line 399):
     ```html
     .logo-placeholder::before {
         content: '💍';
         font-size: 48px;
         animation: float 3s ease-in-out infinite;
     }
     ```
   
   - Replace it with:
     ```html
     .logo-placeholder {
         background-image: url('YOUR_LOGO_URL_HERE');
         background-size: cover;
         background-position: center;
     }
     ```

---

## 📱 Meta Tags for WhatsApp Sharing

The website includes proper Open Graph meta tags. To customize:

1. **Title:** Edit line 6
2. **Description:** Edit line 9
3. **Image:** Edit lines 10 and 13 (as mentioned above)
4. **URL:** Edit line 11 with your actual website URL when deployed

---

## 🌐 How to Update Information Later

To update any information on the website:

1. Open your Google Sheet
2. Edit the cells with new information
3. Save (it auto-saves)
4. Refresh the website - changes appear instantly!

**No need to edit the HTML file!**

---

## 🚀 Deployment Options

### Option 1: GitHub Pages (Free)
1. Create a GitHub account
2. Create a new repository
3. Upload `wedding-website.html`
4. Go to Settings > Pages
5. Select main branch
6. Your site will be live at `username.github.io/repository-name`

### Option 2: Netlify Drop (Free)
1. Go to [Netlify Drop](https://app.netlify.com/drop)
2. Drag and drop your HTML file
3. Instant deployment!

### Option 3: Google Drive + CDN
1. Upload HTML to Google Drive
2. Share as "Anyone with link"
3. Use a service like [drv.tw](https://drv.tw) to convert to direct link

---

## 🎨 Color Customization

The website uses CSS variables for easy color changes. Find this section in the HTML:

```css
:root {
    --beige-primary: #F5F0E8;
    --beige-secondary: #E8DCC8;
    --gold: #D4AF37;
    --gold-dark: #B8941F;
    --gold-light: #F4E4B8;
    --brown: #8B7355;
    --brown-dark: #5C4A3A;
    --text-dark: #2C2416;
}
```

Change these hex codes to customize your color scheme!

---

## 📞 Contact Phone Number Format

Phone numbers in the sheet should be in format: `919650944281` (country code + number, no spaces or symbols)

The website will automatically format them as: `+91 96509 44281`

---

## ✨ Features Included

✅ Bilingual (English/Urdu) with easy toggle
✅ Mobile-responsive design
✅ Google Maps integration for directions
✅ Click-to-call phone numbers
✅ Smooth animations
✅ WhatsApp sharing preview
✅ Easy updates via Google Sheets
✅ Elegant beige and gold theme
✅ Ornate Mughal-inspired design

---

## 🆘 Troubleshooting

**If data doesn't load:**
1. Check if Google Sheet is shared publicly (Anyone with link)
2. Verify the Sheet ID in the HTML matches your sheet
3. Check browser console for errors (F12 key)

**If Urdu text doesn't display:**
1. Ensure you're using proper Urdu unicode text
2. The website uses "Noto Nastaliq Urdu" font which should load automatically

**If maps don't open:**
1. Verify the Google Maps URLs are correct
2. They should start with `https://maps.app.goo.gl/`

---

## 📧 Support

For any issues or customization requests, contact the website developer.

**Enjoy your beautiful wedding website! 💍✨**
