- Motivation für CMS. Für welche Art von Unternehmen/Organisation soll das CMS Verwendung finden? Welche Mehrwerte soll es für die Organisation realisieren.
  
  Wir haben eine moderne und ansprechende Website für den Fußballverein Blau-Weiß Linz entwickelt. Diese Plattform bietet Fans und Interessierten eine Vielzahl von Möglichkeiten, den Verein digital zu erleben. Nutzer können sich die Highlights der letzten Spiele ansehen, Fanartikel direkt im integrierten Online-Shop erwerben und viele weitere spannende Inhalte entdecken. Das Ziel der Website ist es, Blau-Weiß Linz nicht nur finanziell durch Online-Käufe zu stärken, sondern auch neue Fans für den Verein zu gewinnen. 

- Lauffähiges CMS System (z.b. Docker) mit Beispielinhalten (Schwerpunkt sind nicht die Inhalte)
  
  Für unser Projekt haben wir das Framework Hugo verwendet mit dem PaperMod Template:
  
  Funktionen die wir eingebunden haben sind:
  
  - Bilder und Videos: Visuelle Inhalte, die die Website ansprechend und lebendig gestalten.
  - Versionierung: Eine übersichtliche und effiziente Verwaltung der Inhalte.
  - Blog-Integration: Ein Blog, der Updates und spannende Beiträge ermöglicht.
  - Mehrsprachigkeit: Unterstützung für die Sprachen Deutsch und Englisch.
  - Templating: Flexible und wieder verwendbare Layouts.
  - Suchfunktion: Eine intuitive und leistungsstarke Suche.

- Installationsdokumentation
  
  Die Installation von Hugo haben wir anhand der offiziellen Anleitung auf der Hugo-Website durchgeführt. Die Schritte basieren auf der Dokumentation für Windows und sind unter folgendem Link zu finden: [Hugo Installation für Windows](https://gohugo.io/installation/windows/).
  
  ```yml
  baseURL: https://example.org/
  languageCode: en
  title: Double Steininger CMS
  theme: PaperMod
  
  outputs:
    home:
      - "HTML"
      - "RSS"
      - "JSON" #would be required for search i assume - but the fuse js is not working accordingly
  
  params:
    fuseOpts:
      isCaseSensitive: false
      shouldSort: true
      location: 0
      distance: 1000
      threshold: 0.4
      minMatchCharLength: 0
      # limit: 10 # refer: https://www.fusejs.io/api/methods.html#search
      keys: ["title", "permalink", "summary", "content"]
  
  languages:
    en:
      languageName: "English"
      weight: 1
      menu:
        main:
          - identifier: home
            name: Home
            url: /
            weight: 10
          - identifier: search
            name: Search
            url: /search/
            weight: 20
          - identifier: shop
            name: Shop
            url: /shop/
            weight: 30
          - identifier: blog
            name: Blog
            url: /blog/
            weight: 40
          - identifier: about
            name: About Us
            url: /about/v2/
            weight: 50
          - identifier: actualSite
            name: Actual Site 👀
            url: https://blauweiss-linz.at
            weight: 60
    de:
      languageName: "Deutsch"
      weight: 2
      menu:
        main:
          - identifier: home
            name: Home
            url: /
            weight: 10
          - identifier: search
            name: Search
            url: /search/
            weight: 20
          - identifier: shop
            name: Shop
            url: /shop/
            weight: 30
          - identifier: blog
            name: Blog
            url: /blog/
            weight: 40
          - identifier: about
            name: About Us
            url: /about/v2/
            weight: 50
          - identifier: actualSite
            name: Actual Site 👀
            url: https://blauweiss-linz.at
            weight: 60
  ```

        Das yml file spieglt die wichtigsten configurationen in unserem CMS einfach dar,         z.b. die definierten sprachen / menu optionen / search config / theme

- Begründung für die Wahl des Systems
  
  Wir benutzen Hugo da es uns von unserem Professor empfohlen wurden, andere Gründe Hugo zu benützten wären:
  
  Schnelligkeit: Hugo generiert Websites extrem schnell, selbst bei großen Projekten.
  
  Flexibilität: Es unterstützt verschiedene Content-Typen, Templating und erweiterte Funktionen wie Mehrsprachigkeit.
  
  Einfachheit: Die Installation und Nutzung sind unkompliziert, ideal für schnelle Entwicklungsprozesse.
  
  Markdown: Inhalte können einfach in Markdown geschrieben werden.

- Beschreibung wie Sie die Anforderungen (Muss, Kann, Vorschläge) jeweils abgebildet haben.
  
  Inhaltsverwaltung: In Form von Markdowns und statischen Assets.
  
  Templating und Version: Mit den von Hugo gelieferten Inhalten.
  
  Suchfunktion: In Form vom Template.
  
  Mehrsprachigkeit und Internationalisierung: Im Form von Template.
  
  Responsive Design: In Form vom Template.
  
  Social-Media Integration: Als Content im Markdown 
  
  SEO-Optimierung:  fuse.js
  
  All diese Dinge mussten wir Konfigurieren damit sie Ordnungsgemäß funktionieren 