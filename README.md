# MavoGames website

Homepage and demo page for mavogames.com. Plain HTML, CSS and JavaScript, no build step.

## Files
- `index.html` – homepage (intro, hero game, products, Playground demo video, sample games, Studio, contact form)
- `demo.html` – demo page brands reach after booking a demo (email sign-in, video, Try Playground, Book a guided demo)
- `img/` – sample game phone screenshots
- `media/playground-demo.mp4`, `media/playground-poster.jpg` – Playground walkthrough video and its poster

Run locally: `python3 -m http.server 8000` in this folder, then open http://localhost:8000

## Hosting
Live on Netlify (project: **mavogames**, mavogames.netlify.app). Domain mavogames.com is at GoDaddy:
- A record `@` → `75.2.60.5`
- CNAME `www` → `mavogames.netlify.app`
To update: Netlify → project → Drop new files → drop this folder or its ZIP.

## Contact form → Google Form
The form posts to the Google Form "MavoGames: Book a demo" (responses also land in the linked Sheet).
Config is the `GFORM` object near the end of `index.html`:
- `brand` entry.35950745
- `dept` entry.1956042275 (Department / function)
- `email` entry.1232570687
- `phone` entry.1932040005 (optional)
- `metric` entry.178479602 (App installs, Sign-ups, Brand recall, Something else)
Don't delete or reorder the form's questions; renaming is fine. Submissions only work on the live domain, not from a local file.

## Demo page
After a successful submit, the visitor's email and brand are saved in their browser (localStorage key `mavogames_demo_user`) and they're sent to `demo.html`. Returning visitors sign in by typing their work email. This is a lightweight gate, not a verified login; a real login (emailed sign-in link) needs an auth service.

Links to set at the top of the script in `demo.html`:
- `PLAYGROUND_URL` – the hosted MavoGames Playground builder (currently the Claude artifact)
- `BOOKING_URL` – a Google Calendar appointment page for guided demos (empty = button goes back to the contact form)

## To do
- Final Playground builder link, renamed from "Studio" to "Playground" inside the builder
- Booking link for guided demos
- Real email login (optional, later)
- Privacy policy and terms pages; og:image for link previews
