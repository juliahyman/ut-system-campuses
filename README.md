# UT System Campuses: a story map

An interactive [StoryMapJS](https://storymap.knightlab.com/) tour of the five University of Tennessee System campuses, hosted on GitHub Pages.

**Live site:** https://juliahyman.github.io/ut-system-campuses/
**Text version:** https://juliahyman.github.io/ut-system-campuses/text.html

This is a revised version of the [original Knight Lab draft](https://uploads.knightlab.com/storymapjs/05be4ebf95d6444371e14069b6f9ccf8/ut-system-campuses/draft.html).

## What changed and why

### Accuracy fixes
| Slide | Original | Revised |
|---|---|---|
| UT Memphis | Linked to the **University of Memphis** Wikipedia page, which is a different school outside the UT System | Renamed to its official name, **UT Health Science Center**. Added a note explaining it is not the University of Memphis. |
| UT Memphis | Established 1912 | **1911**, when UT moved its medical and dental departments from Nashville to Memphis (per UTHSC and the Tennessee Encyclopedia) |
| UT Martin | "Founded in 1900 by a Tennessee Baptist Convention" | 1900 was the founding of **Hall-Moody Institute**, an earlier school on the same site. UT took over the site in **1927** as UT Junior College. It became UT Martin in 1967. |
| UT Knoxville | Source link had a trailing period (`fact-book/.`) | Fixed the link |
| Overview | "five locations" | Explains the five campuses *and* the statewide institutes |

### Story and structure
- **A clear story:** slides now follow the order each campus *joined UT* (1794 → 1911 → 1927 → 1969 → 2021). Each slide shows that year in the date field, so the orange path traces how the system grew.
- **The same facts for every campus:** each slide gives the founding or joining year, the campus's role, its Fall 2025 enrollment from one source (the UT System release, where the campuses add up to 64,866), and its mascot. The original had statistics only for Knoxville.
- **New slides:** "Beyond the five campuses" (UT Space Institute, UT Institute of Agriculture, Institute for Public Service) and "Sources & further reading."
- **Better zoom:** campuses are shown at zoom 15 so you can see the campus itself, not just the city.
- **Custom markers:** each kind of site has its own map pin (in [`markers/`](markers)): an orange pin for the four main campuses, an orange pin with a cross for the Health Science Center, a gray star for the statewide institutes, and a gray "i" for the sources slide.

### Media
- Replaced the Giphy GIFs, a low-resolution Google thumbnail, and the embedded Wikipedia pages with **freely licensed Wikimedia Commons photos**. Each photo has a photographer and license credit.
- Every image has a caption that describes it.

### Accessibility and publishing
- Added a **text version** (`text.html`) built from the same `storymap.json`, so it never gets out of sync with the map. It works with screen readers and on slow connections.
- Added a page title, description, and social-preview metadata; a fallback message if JavaScript fails; and UT orange for the route line.
- Removed the Knight Lab analytics tag from the embed.

## Ideas for further expansion
1. **Satellite locations:** UTHSC's sites in Knoxville, Chattanooga and Nashville; UTM's centers in West Tennessee; and UT Extension's 95 county offices.
2. **Short audio or video clips:** for example, a student from each campus.
3. **Comparison chart:** enrollment over time for each campus on a closing slide.
4. **Primary sources:** historic photos from UT Libraries' digital collections, such as Blount College or Hall-Moody Institute.

## Editing
All content is in [`storymap.json`](storymap.json). It uses StoryMapJS's standard format, so you can edit it by hand or paste it into a Knight Lab StoryMap. `index.html` loads StoryMapJS 0.9.6 from Knight Lab's CDN and renders the JSON.

To change a slide's map pin, edit its `location` in `storymap.json`: `"use_custom_marker": true, "icon": "markers/<name>.svg", "iconSize": [36, 46]`.

To preview locally, run `python -m http.server` in this folder and open http://localhost:8000. Opening the file directly won't work, because browsers block `fetch()` for `file://` pages.
