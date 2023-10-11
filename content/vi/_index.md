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
        label: '**Tìm hiểu thêm**'
        url: '#overviews'
      text: |-
        # Máy gia tốc HUS Pelletron, ĐH Khoa học tự nhiên, ĐHQG Hà Nội
        {style="color: white"}
        
        ##### Máy gia tốc NEC 5SDH-2 Tandem Pelletron. Hệ máy gia tốc dùng cho nghiên cứu cơ bản đầu tiên và duy nhất của Viêt Nam. Ứng dụng các kỹ thuật phân tích dùng chùm ion (Ion beam analysis) và cấy ion (MeV-ion implantation) trong nghiên cứu vật liệu, môi trường, địa chất v.v ...
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
        - name: Thông tin chung
          tag: Overview
        - name: Nguồn ion
          tag: Ion Sources
        - name: Các kênh ra
          tag: Beamlines
        - name: Nghiên cứu và Ứng dụng
          tag: Research and Applications
        - name: Đào tạo
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
      title: Công bố khoa học
      subtitle: ''
      text: |-
        <h2> Danh sách các công bố khoa học có sử dụng chùm tia từ máy gia tốc HUS Pelletron:</h2>
        <br>[BibTeX]({{< ref "../en/publication_list.bib">}}) </br>
        <p></p>
        <div id="element"></div>
        <script type="text/javascript">
            async function getData(url) {
                const response = await fetch(url);
                return response.json();
            }
            window.onload = async function () {
                const jsondata = await getData("../en/publication_list.json")
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
    design:
      columns: '1'

  - block: collection
    id: posts
    content:
      title: Tin tức
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
      title: Thư viện Ảnh
      subtitle: ''
      text: |-
        {{< gallery album="photoalbum1" >}}
    design:
      columns: '1'
  - block: contact
    id: contact
    content:
      title: Liên hệ
      subtitle:
      text: |-
        Phòng thí nghiệm Máy gia tốc, Bộ môn Vật lý Hạt nhân, Khoa Vật lý
      # Contact (add or remove contact options as necessary)
      email: 05.nghia@gmail.com
      phone: +84 24 3558 3980
      # appointment_url: 'https://calendly.com'
      address:
        street: Tầng 1, toà nhà T10, Đại học Khoa học Tự nhiên Hà Nội, 334 Nguyễn Trãi, Thanh Xuân
        city: Hà Nội.
        postcode: '120062'
        country: Vietnam
        country_code: VN
      office_hours:
        - 'Thứ 2 - Thứ 6 8:00 to 16:00'
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
          # Enable CAPTCHA challenge to reduce spam?
          captcha: false
    design:
      columns: '2'
  - block: markdown
    id: peoples
    content:
      title: 
      subtitle: ''
      text: '[Danh sách các nhân sự tại phòng thí nghiệm máy gia tốc]({{< ref "peoples">}})'
    design:
      columns: '1'      
  - block: tag_cloud
    content:
      title: Các chủ đề
    design:
      columns: '2'
---
