# Blind spots (technical, check these every run)

Issues that slip through reviews again and again. Add your own at the bottom.

## Language and formats (growth, design, tech)
- **Bilingual sites with a JavaScript toggle on one URL**: the second language does not exist for search engines.
  And some text always stays in the wrong language: title, meta description, alt texts, placeholders,
  dropdown options, error messages, footer, emails
- **Number and currency formats**: "1.500" reads as one and a half in English, "1,500" as one and a half in
  many European and Latin American locales. Match the reader's locale, or write numbers in a way that cannot be misread
- **Dates and times** without a time zone on bookings or launches

## Forms and flows (user tester, tech)
- **Form field mapping by position**: code that reads a dropdown by `selectedIndex` breaks silently as soon as an
  option is added. Map by value
- **No success or error state**: after submit nothing visibly happens, or errors wipe the filled-in fields
- **Placeholders used as labels**: the label disappears while typing
- **Mobile keyboards**: email and phone fields without the right input type
- **Thank-you or confirmation page** reachable directly by URL, or saying something different from the offer

## Weight and assets (tech)
- **The same image or video downloaded more than once** (different sizes of one file, or a preload plus a
  normal load)
- **Huge images scaled down in the browser**, videos that autoplay on mobile data
- **Missing social preview**: no Open Graph image, title or description, so shared links look broken
- **Missing favicon, 404 page, or robots and sitemap that contradict each other** (a `noindex` page in the sitemap)

## Your blind spots
<!-- Add new ones here -->
