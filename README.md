# Quote of the Day Card
![quote](images/quote.PNG)

Quote of the Day card uses the [Feed Parser Sensor](https://github.com/custom-components/sensor.feedparser) to pull quotes from Brainyquotes.com RSS feed and display them on a nice card. Quotes are selected randomly.

## Instructions
 1. Download the [Feed Parser Sensor](https://github.com/custom-components/sensor.feedparser) and use the following configuration:

 ```yaml
sensor:
  - platform: feedparser
    name: Quote of the Day
    feed_url: 'https://www.brainyquote.com/link/quotebr.rss'
    date_format: '%a, %b %d %I:%M %p'
```
 2. Download the [Quote-Day-Card](https://raw.githubusercontent.com/dnguyen800/Quote-of-the-Day-Card/master/quote-day-card.js), [bg.jpg](https://github.com/dnguyen800/Quote-of-the-Day-Card/raw/master/images/bg.jpg) and place the files in your `config/www` folder.
 
 3. Add the following to the resources section of your ui-lovelace.yaml

```yaml
resources:
  - url: /local/quote-day-card.js?v=0
    type: js  
```
4. Write configuration for the card in your `ui-lovelace.yaml`.

```yaml
 - type: custom:quote-day-card               
   entity: sensor.quote_of_the_day
```

5. Restart Home Assistant
 
## Options
| Name | Type | Default | Description
| ---- | ---- | ------- | -----------
| entity | string | **Required** | Name of the Feed Parser sensor that contains the Quote of the Day data.
| image | string | /local/bg.jpg | If the background image is stored in a location other than /www/bg.jpg, you can input a different location here. Example: '/local/bg.jpg'


## Credits
 - Background image by [Yannick Pulver](https://yannickpulver.com/) via [Unsplash](https://unsplash.com/@yanu)
 - [Feed Parser Sensor](https://github.com/custom-components/sensor.feedparser) - For doing the hard work
 - All the Home Assistant custom components and cards out there. I learned from your examples.
 
