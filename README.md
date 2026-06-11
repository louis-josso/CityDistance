# Meet in the Middle

Find where two people can both live, based on how long it actually takes each of them to get to work by public transport or bike. Distance in a straight line is useless for this; what matters is travel time.

Drop a pin on each job, set how far each person is willing to travel, and the **green zone** shows every neighbourhood reachable by both. It also works as a fair place to meet up. Works in any city with OpenStreetMap transit coverage, and defaults to Berlin.

**[→ Open the app](https://louis-josso.github.io/CityDistance/)**

### Features

- Two draggable pins, one per person, each with its own time budget.
- Travel by **transit or bike**, chosen per person.
- A **[group version](https://louis-josso.github.io/CityDistance/group.html)** for up to 5 people, where the green zone is reachable by everyone.
- **Shareable links**: copy a link that reopens the exact map, pins and settings included.
- City picker grouped by country, or jump to your current location.

---

Built with [Leaflet](https://leafletjs.org/), [Turf.js](https://turfjs.org/), and the [Geoapify Isoline API](https://www.geoapify.com/isoline-api/). No backend, everything runs in the browser.

Made by [Louis Josso](https://www.linkedin.com/in/louisjosso/).
