# WWWRPG

The idea is to let you explore the web via an rpg. The app will parse a website and use the parsed data to build a game world for the user to interact with.

How well the game works will depend on the page visited having semantic markup and the usage of schemas.

### Game setting ideas

- Space? Each website could be a planet
- Zelda-like setting
- City setting

### Game mechanics (WIP)

- The user will explore the page and travel to different pages/sites through links/portals
- The user gains XP by reading/interacting with page contents
- The user will battle monsters generated by elements on the page
- The user can purchase products/items from mercheants/vendors if the site has any product schemas
- The user can view media on the page in some way (images/videos/audio)

### Implementation Ideas

The user lands on a game screen generated by detecting the following:

- `<title>` will display as the kingdom/planet/domain you're on.
- `<meta>` can be used to provide information about the world
    - lang can be used to show a little flag for the language
    - desc can be used to display info about the kingdom. Maybe by the mayor/leader.
    - favicon/icons can be used as the badge/banner for the place.
    - Twitter/facebook usernames can be used to fetch further data
    - schemas (see below)
- `<h1>` will display the current subscreen. (house, asteroid/moon)
- `<a>` on a page will be portals/doors to other screens
- `<nav>` elements should group portals/doors together
- `<article>` can be a person with information
- `<section>` could group together contents somehow
- `<forms>` could be bureoucrats/mercheants
- `<audio>` Could potentially play in the background, or be triggered in some other way

### manifest.json

If the site is a PWA or has a `manifest.json` file, this can be a source of colors, banners etc.

### Schemas

If the crawler detects any schemas on the page, these will work great for certain things:

- Person (http://schema.org/Person) Used for NPC's (see below)
- Articles
- Products
- Local businesses - Used for Mercheants
- ...

### Interactive NPC's

IF the user approaches an <article> or a Person schema, the dialogue will be based on the article contents.

Example:
Name: (article author - based on http://schema.org/Person).
Hello, traveller!
    - 1: What can you tell me? <
    - 2: Take me somewhere
    - 3: I have to go
    
Option 1 will print out the article contents one bulk at a time. Upon completion the user can gain more XP.
Option 2 will display any links in the article and allow the user to go there
Option 3 will end the conversation


### Enemies and battles

Once in a while, a detected Person (or something else) can be used as an enemy. 

### The CSS

The css can be parsed and the following information can be extracted from it:
- Colors to be used in the world
- Fonts to be used in the UI

### The JS

The javaScript could potentionally be crawled to get some info to be used in the world:
- Frameworks in use (used to create monsters etc?)
- Size of the bundle (strength of the monsters? Size of the world?)
- XHR calls (???)

### Other Ideas

Other page elements that could potentially be represented ingame:

- Carousels (A carousel?)
- Accordions (???)
- Videos (Played through conversation?)
- 
