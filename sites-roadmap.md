# Foundation For Sites Roadmap

## 6.2.4: RC 10/06, Full Release 10/20


**Release Name: Mimas**

<img width="100" src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/bc/Mimas_Cassini.jpg/1280px-Mimas_Cassini.jpg"></img>

Mimas is a moon of Saturn which was discovered in 1789 by William Herschel. It is named after Mimas, a son of Gaia in Greek mythology, and is also designated Saturn I.
With a diameter of 396 kilometres (246 mi) it is the smallest astronomical body that is known to be rounded in shape because of self-gravitation.


**Narrative:**  Improve keyboard-based accessibility throughout the framework.

Left To Do:

1. Catch up on PRs
2. QA For Release

## 6.3: RC 11/24, Full Release 12/8(tentative)
**Narrative:** Expand the usability and options of tabs and accordions, especially on mobile and keyboard devices.

**Agenda:**

1. Tabs Deep Linking (+ unit testing)
2. Accordion deep linking (+ unit testing) 
3. Responsive accordion (+ unit testing) 
4. Cards (+ unit testing)
5. Drilldown responsive heights (+ unit testing)
6. Keyboard and other ARIA improvements
7. (optional) Vertical Rhythm Mode
8. Joyride
9. QA For Release


## 6.3.1: RC 1/19, Full Release 2/2 (tentative)
**Narrative:**  Additional functionality and bug fixes for the most commonly used Javascript components.

**Agenda:**

1. Dropdown positioning Fix
2. Sticky (bugfixes + unit testing) 
3. Drilldown (bugfixes + unit testing)
4. Orbit (Bugfixes + unit testing) 
5. Fix template issues 
6. QA For Release


## 6.3.2: Tentative Date: Feb/March
**Narrative:** Unifying lifecycle and event handling across all javascript plugins

**Agenda:**
1. Unified events
2. Unified callback/lifecycle hooks

## 6.4: Tentative Date: May
**Narrative:** Moving Apps-specific components into Sites to pave the way for Foundation Everywhere

**Agenda:**

1. Clearing
2. ES2015 (ES6) Module dependencies
3. Yeoman Generator
4. Backport Apps grid into Sites
5. Backport Panel into Sites

## 6.5: Tentative Date: July
**Narrative:** Pluggable Building Blocks:  Enable building and importing compound components (e.g. cards or full navbars) that automatically fit your design.

**Agenda:** 

1. Specification for building blocks to make them ‘automatically’ fit your design 
2. Building Block site refresh
3. Update Foundation CLI to enable importing building blocks.


## 7.0 Considerations

**The future:  Foundation Everywhere**

We don’t think Foundation should pick a javascript framework, rather it should be accessible in every framework.  This is learning from challenges and mistakes made while making Foundation for Apps.  We believe we should be supporting common Apps use cases but not "picking a winner" in terms of JavaScript framework. Instead we should work with the community to achieve high quality integrations in every framework.

1. Angular 1 -- Exists
2. React -- Exists
3. Ember.js -- Exists
4. Angular 2
5. Polymer


## Other Things to Investigate/Schedule

1. PostCSS - would there be a benefit to moving to PostCSS?  What would we want to do with this?
2. Progressive Web Apps - are there utilities that make sense as a part of Foundation for Sites that would help support this
3. CSS Grid - Not sure what the timeline is on this but we should target this, perhaps similar to flexbox mode?
4. Styleguides - We already include some styleguide stuff in the template, but is there more we can do here?
5. Themes - Enabling better 'Out of the box' use for non-designers
6. Tooling to enable more interesting things with SVGs. Ideas include a way to auto-inline to make inner elements accessible to CSS, and some common effects (fills/borders/etc tied in with your pallete, etc)
