# meetups.cologne

## Getting started
```
$ bundle install
$ middleman server
```

## Adding a meetup
All the meetup data is generated from the `meetups` list in `data.dates.yaml`. To add a meetup, simply add a new entry to the list.  
__NOTE: There should never be more than 4 Meetups on a page. Adding more then 4 meetups will break the layout.__  
Every meetup needs the following attributes:
``` yaml
    name: "Webmontag"
    next_date: "10.04.2017"
    logo: "logo_webmontag.svg"
    gradient_from: "#33D4A6"
    gradient_to: "#3FDA90"
    badge_color: "#FF7400"
    link: "http://webmontag-koeln.de/"
    display_name: true
    dark_button: false
```

* `name`: The name of the meetup
* `next_date`: The date of the next meeting. If none is know, it can be a short text like "tba"
* `logo`: The logo of the meetup. The File needs to be located in the `images` folder
* `gradient_from` & `gradient_to`: Start and end point of the background gradient. If you need a solid color, use the same color for both fields.
* `badge_color`: Color of the badge. Keep in mind that the text on the badge is always white while choosing the color.
* `link`: Link to an external page representing the meetup.
* `display_name`: Wether the name of the Meetup should be displayed. This also affects the size of the logo. **Can only be `true` or `false`.**
* `dark_button`: Wether to use a dark button. Use this if the background color is light. **Can only be `true` or `false`.**
