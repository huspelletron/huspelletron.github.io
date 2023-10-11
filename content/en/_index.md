---
# Leave the homepage title empty to use the site title
title:
date: 2022-10-24
type: landing

sections:
  - block: hero
    id: home
    content:
      title: 
      cta:
        label: '**Learn More**'
        url: '#overviews'
      text: |-
        # HUS Pelletron Accelerator Laboratory
        {style="color: white"}
        
        ##### NEC 5SDH-2 Tandem Pelletron Accelerator: The first and only research accelerator in Vietnam, featuring modern Ion Beam Analysis and MeV-ion implantation techniques for various applications in Nuclear, Materials, Environmental, and Geological Sciences, ...
        {style="color: white"}
        
        # <!--Custom spacing-->
        # <div class="mb-3"></div>
        # <!--GitHub Button JS-->
        # <script async defer src="https://buttons.github.io/buttons.js"></script>
    design:
      text:
        text_color_light: true
      background:
        image:
          filename: bg.jpeg
          filters:
          # Darken the image? Range 0-1 where 1 is transparent and 0 is opaque.
            brightness: 1.
           #  Image fit. Options are `cover` (default), `contain`, or `actual` size.
            size: cover
            # Image focal point. Options include `left`, `center` (default), or `right`.
            position: center
            # Use a fun parallax-like fixed background effect on desktop? true/false
            parallax: true
            # Text color (true=light, false=dark, or remove for the dynamic theme color).
            text_color_light: true
        # gradient_end: '#1976d2'
        # gradient_start: '#004ba0'
        # text_color_light: true

  - block: portfolio
    id: overviews
    content:
      title: 
      filters:
        folders:
          - overview
      # Default filter index (e.g. 0 corresponds to the first `filter_button` instance below).
      default_button_index: 0
      # Filter toolbar (optional).
      # Add or remove as many filters (`filter_button` instances) as you like.
      # To show all items, set `tag` to "*".
      # To filter by a specific tag, set `tag` to an existing tag name.
      # To remove the toolbar, delete the entire `filter_button` block.
      buttons:
        # - name: All
        #   tag: '*'
        - name: General
          tag: Overview
        - name: Ion sources
          tag: Ion Sources
        - name: Beamlines
          tag: Beamlines
        - name: Research and Applications
          tag: Research and Applications
        - name: Education
          tag: Education
    design:
      # Choose how many columns the section has. Valid values: '1' or '2'.
      columns: '1'
      view: showcase
      # For Showcase view, flip alternate rows?
      flip_alt_rows: false
      sort_by: 'Date'

  - block: markdown
    id: featured
    content:
      title: Publications
      subtitle: ''
      text: |-
        <h2> List of published research works ultilizing ion beams from the HUS Pelletron Accelerator:</h2>
        <p></p>
        <div id="element"></div>
        <script type="text/javascript">
            async function getData(url) {
                const response = await fetch(url);
                return response.json();
            }
            window.onload = async function () {
                const jsondata = await getData("publication_list.json")
                let Cite = require('citation-js')
                let bibliography = "<ol>";
                    for (let i in jsondata.citations) {
                        let cite = await Cite.async(jsondata.citations[i])
                        let bibliography_i = cite.format('bibliography', {
                            format: 'html',
                            template: 'apa',
                            lang: 'en-US'
                        })
                        if (jsondata.urls[i]!="")
                            bibliography += "<li>" +"<a href=\""+ jsondata.urls[i] + " \"target=\"_blank\">"+bibliography_i + "</a></li>"
                        else
                            bibliography += "<li>" +bibliography_i + "</li>"
                    }
                    bibliography+="</ol>"
                    let element = document.getElementById('element')
                    element.innerHTML = bibliography
                    _altmetric_embed_init()
                }        
        </script>
        <br/>

        * Autmatically generated from BibTeX file [here]({{< ref "../en/publication_list.bib">}}) *
    design:
      columns: '1'

  - block: collection
    id: posts
    content:
      title: News
      subtitle: ''
      text: ''
      # Choose how many pages you would like to display (0 = all pages)
      count: 5
      # Filter on criteria
      filters:
        folders:
          - post
        author: ""
        category: ""
        tag: ""
        exclude_featured: false
        exclude_future: false
        exclude_past: false
        publication_type: ""
      # Choose how many pages you would like to offset by
      offset: 0
      # Page order: descending (desc) or ascending (asc) date.
      order: desc
    design:
      # Choose a layout view
      view: compact
      columns: '2'
  - block: markdown
    id: gallery
    content:
      title: Gallery
      subtitle: ''
      text: |-
        {{< gallery album="photoalbum1" >}}
    design:
      columns: '1'
  - block: contact
    id: contact
    content:
      title: Contact
      subtitle:
      text: |-
        Accelerator Laboratory, Department of Nuclear Physics, Faculty of Physics
      # Contact (add or remove contact options as necessary)
      email: 05.nghia@gmail.com
      phone: +84 24 3558 3980
      # appointment_url: 'https://calendly.com'
      address:
        street: 1st Floor, T10 building, 334 Nguyen Trai Street
        city: Hanoi
        postcode: '120062'
        country: Vietnam
        country_code: VN
      office_hours:
        - 'Monday-Friday 8:00 to 16:00'
      # contact_links:
      #   - icon: twitter
      #     icon_pack: fab
      #     name: DM Me
      #     link: 'https://twitter.com/Twitter'
      #   - icon: skype
      #     icon_pack: fab
      #     name: Skype Me
      #     link: 'skype:echo123?call'
      #   - icon: video
      #     icon_pack: fas
      #     name: Zoom Me
      #     link: 'https://zoom.com'
      # Automatically link email and phone or display as text?
      autolink: true
      # Email form provider
      form:
        provider: formspree
        formspree:
          id: moqoyqwl
          captcha: true
          captcha_key: 6LfWWpEoAAAAAI2s-bhACVbEGBFrkHmO1BSTvwRP
        netlify:
          Enable CAPTCHA challenge to reduce spam?
          captcha: false
    design:
      columns: '2'
  - block: markdown
    id: peoples
    content:
      title: Peoples
      subtitle: ''
      text: '[Current staff members of the HUS Pelletron Accelerator Laboratory]({{< ref "peoples">}})'
    design:
      columns: '2'      
  - block: tag_cloud
    content:
      title: Popular Topics
    design:
      columns: '2'
---
