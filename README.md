# Bluetide Hotel - Hotel Room Booking UI

Micro project for **Responsive Web Page Design (DI03000061)**.
A responsive hotel booking interface built with **Bootstrap 5.3**: room selection, reservation and confirmation messages.

Frontend only. There is no server and no database. Bookings are kept in the browser with `localStorage`.

## How to run

Open `index.html` in a browser. Everything (Bootstrap, icons, fonts, photos) is inside the folder, so it works without internet.

## Pages

| Page | File | What it does |
|---|---|---|
| Home | `index.html` | Hero with availability search, featured rooms, live availability bars, reviews |
| Rooms | `rooms.html` | Filter, sort and page through 8 room types, details modal, comparison table |
| Book a room | `booking.html` | 3-step reservation form, live price summary, save confirmation, confirmation message |
| My bookings | `my-bookings.html` | Table of saved bookings, view details, cancel with delete confirmation |
| Gallery | `gallery.html` | Carousel with 9 photos, activities, timetable tables |
| About | `about.html` | Story, location, team, daily timetable, policies, questions |
| Contact | `contact.html` | Notices, contact form, service desks |

## The booking flow (for the demo)

1. Home: pick dates and guests, press **Show available rooms**.
2. Rooms: filter or sort, press **Select** on a room.
3. Book a room: fill step 1 and step 2, apply the code `TIDE15` in step 3, tick the policy box, press **Confirm reservation**.
4. A modal asks **Save this reservation?** Press **Save reservation**.
5. The confirmation card and a green alert appear. Closing the alert shows a toast message.
6. My bookings: the new row is highlighted. Press **Cancel** to see the delete confirmation modal.

## Where each practical from the index is used

Bootstrap 5 renamed a few Bootstrap 3 components. The names used here are: Glyphicons -> Bootstrap Icons, panel -> card, label -> badge, jumbotron -> hero section built with utilities, thumbnail -> `img-thumbnail` and cards, media object -> flex utilities (`d-flex`).

| No. | Practical | Where to find it |
|---|---|---|
| 1 | Install Bootstrap, required files | `assets/vendor/bootstrap`, `assets/css/main.css`, `<head>` of every page |
| 2 | Centre a name with Bootstrap | `text-center mx-auto` heading block, `index.html` "Three rooms guests book most" |
| 3 | `container` and `container-fluid` | `about.html`: full-width facts band (fluid) above the fixed-width content |
| 4 | Offset, reordering, nesting columns | `index.html` hero (`offset-lg-1`); `about.html` "The place" (`order-lg-*`, nested row) |
| 5 | Timetable with the grid system | `about.html` "The daily timetable" |
| 6 | Activities with image styles and table styles | `gallery.html`: six activities (rounded, thumbnail, circle, shadow, figure) and three tables; `rooms.html` comparison table (striped, hover, bordered, coloured row) |
| 7 | Typography | `about.html` "Our story": display heading, lead, mark, abbr, blockquote, description list, small |
| 8 | Form layout, controls, buttons | `booking.html` (all three steps), `contact.html` |
| 9 | Dropdown menus, drop-up, headers, icons | Navbar "Bookings" menu; `rooms.html` sort menu (right-aligned, headers, dividers); footer language menu (drop-up); Bootstrap Icons everywhere |
| 10 | Button groups and button toolbar | `rooms.html` filter toolbar: type group, guests group with nested dropdown, view group |
| 11 | Input groups | Home search card, `booking.html` (dates, +/- counters, +91, @, offer code with button), `contact.html` |
| 12 | Navigation tabs / pills | `booking.html` step pills; `about.html` policy tabs |
| 13 | Navbar fixed to top, bar fixed to bottom | Top navbar on every page (logo, menu, dropdown, search, sign-up); bottom bar appears below 992 px width |
| 14 | Breadcrumb, pagination, badge, page header, thumbnails | `rooms.html` (all five); breadcrumbs on every inner page |
| 15 | Progress bars (label, striped, animated, multi-colour, changed by JavaScript) | `index.html` "How full we are tonight" + Refresh button; `booking.html` step progress bar |
| 16 | Media objects, rounded, nested | `about.html` "Who looks after you" (three levels); `index.html` reviews with nested reply |
| 17 | Panels, list groups, alerts, message after an alert is closed | `contact.html` service desks and notices; `booking.html` price summary; every alert shows a toast when closed |
| 18 | Smooth page transition | `<main id="page">` fades in and out with `.fade` / `.show` (see `assets/js/app.js`) between all pages |
| 19 | Modals for save and delete confirmation | `booking.html` "Save this reservation?"; `my-bookings.html` "Cancel this booking?" |
| 20 | Scrollspy, tooltip, collapse, popover | `about.html`: side menu (scrollspy), photo tooltips, accordion and collapse, popovers on "photo ID" and "GST" |
| 21 | Carousel photo gallery (minimum seven) | `gallery.html`: nine slides with indicators, captions, fade and thumbnails |
| 22 | Header and footer with utility classes | Navbar and footer on every page (spacing, flex, colour, link utilities) |
| 23 | Customizing Bootstrap with Sass | `scss/main.scss`: variables overridden before `@import "bootstrap"` |
| 24 | Customizing components and themes | `scss/main.scss` part 4, plus the light / dark theme button in the navbar |
| 25 | Website with five to seven pages (Hospitality) | The whole project: seven pages |

## Folder structure

```
index.html, rooms.html, booking.html, my-bookings.html, gallery.html, about.html, contact.html
assets/
  css/main.css            compiled Bootstrap + theme (do not edit by hand)
  js/data.js              room list, prices, helper functions
  js/app.js               code shared by all pages (theme, tooltips, transitions, toasts)
  js/home.js, rooms.js, booking.js, bookings.js, gallery.js, contact.js
  img/                    photos
  fonts/                  Manrope and Marcellus web fonts
  vendor/                 Bootstrap JS bundle and Bootstrap Icons
scss/main.scss            the Sass source of the theme
package.json              only needed to rebuild the CSS
```

## Rebuilding the CSS (optional, for Practical 23)

Needs Node.js.

```
npm install
npm run css
```

Change `$primary` at the top of `scss/main.scss`, run `npm run css` again, and the whole site changes colour.

## Notes

- Bluetide Hotel is fictional. The address, phone number, prices and reviews are invented for the project.
- GST rule used in the price summary: 5% when the room rate is up to Rs 7,500 a night, 18% above that.
- Photos are Unsplash photos, taken from two open-source GitHub projects that credit Unsplash:
  `john-smilga/react-beach-resort-project` (rooms, pool) and `learning-zone/website-templates` (lobby, bar, banquet hall, reception, garden).
- Bootstrap 5.3.3 and Bootstrap Icons 1.11.3 are MIT licensed. Fonts: Manrope and Marcellus (SIL Open Font License).
