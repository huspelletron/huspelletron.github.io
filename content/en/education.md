---
# Leave the homepage title empty to use the site title
title: Ion Sources
date: '2018-06-28T00:00:00+01:00'
draft: false
share: false
commentable: false
editable: false
type: landing

sections:
  - block: portfolio
    id: overviews
    content:
      title: 
      filters:
        folders:
          - overview
      # Default filter index (e.g. 0 corresponds to the first `filter_button` instance below).
      default_button_index: 4
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
---
