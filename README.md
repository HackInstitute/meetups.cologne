# meetups.cologne

## Getting started
```
$ git clone git@github.com:HackInstitute/meetups.cologne.git
$ bundle install
$ middleman server
```

This will run the app using whatever data is specified in `data/master.yaml`.

### Using a city specific set of data
To run the app using the data of a specific city, you need to pass the name of that city to the middleman as an environment variable.

```
$ CITY=‘london’ middleman server
```

Or, if you're using bundler:

```
$ City='london' bundle exec middleman server
```

Note that the name must match a `.yaml` file with an equal name.

## Adding a new city
To add a new city, simply add a new `.yaml` file in the `data` folder with the name of you city.  
The file should have the following structure:
``` yaml
city_name: #the name of your city
  title: london
  url: http://www.meetups.london
  social_media_image: http://www.meetups.london/images/meetups-london-image.jpg #must be places in /images
  analytics:
    - meetups.amsterdam
    - meetups.cologne
  meetups: #max 4, or the layout will break
    -
      name: "PyData London Meetup"
      next_date: "07.03.2017"
      logo: "pydata.png"
      gradient_from: "#576C74"
      gradient_to: "#576C74"
      badge_color: "#FF7400"
      link: "https://www.meetup.com/PyData-London-Meetup"
      display_name: false
      dark_text: false
    -
      name: "London JavaScript Community"
      next_date: "06.03.2017"
      logo: "londonjs.png"
      gradient_from: "#2C2D2A"
      gradient_to: "#2C2D2A"
      badge_color: "#EFD738"
      link: "https://www.meetup.com/London-JavaScript-Community"
      display_name: false
      dark_text: false
    -
      name: "InsTech London"
      next_date: "20.03.2017"
      logo: "instech.jpeg"
      gradient_from: "#1B1B19"
      gradient_to: "#1B1B19"
      badge_color: "#F1D72A"
      link: "https://www.meetup.com/instech/"
      display_name: false
      dark_text: false
    -
      name: "London New Tech"
      next_date: "08.03.2017"
      logo: "london_new_tech.png"
      gradient_from: "#FF7403"
      gradient_to: "#FF7403"
      badge_color: "#FFC48E"
      link: "https://www.meetup.com/London-New-Tech/"
      display_name: false
      dark_text: false    
```


## Adding a meetup
All the meetup data is generated from the `meetups` list in `data.dates.yaml`. To add a meetup, simply add a new entry to the list.  
__NOTE: There should never be more than 4 Meetups on a page. Adding more then 4 meetups will break the layout. (Well, not actually break because flexbox is so awesome, but it won't look any good.)__  
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
    dark_text: false
```

* `name`: The name of the meetup
* `next_date`: The date of the next meeting. If none is know, it can be a short text like "tba"
* `logo`: The logo of the meetup. The File needs to be located in the `images` folder
* `gradient_from` & `gradient_to`: Start and end point of the background gradient. If you need a solid color, use the same color for both fields.
* `badge_color`: Color of the badge. Keep in mind that the text on the badge is always white while choosing the color.
* `link`: Link to an external page representing the meetup.
* `display_name`: Wether the name of the Meetup should be displayed. This also affects the size of the logo. **Can only be `true` or `false`.**
* `dark_text`: Wether to use a dark title text & button. Use this if the background color is light. **Can only be `true` or `false`.**
