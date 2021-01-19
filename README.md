# humidifier-card
> Humidifier card for Home Assistant Lovelace UI



## Installing
Download humidifier-card.js file.<br>
Put humidifier-card.js file into your config/www folder.<br>
Add a reference to humidifier-card.js in Lovelace. There's two way to do that:<br>
Using UI: Configuration → Lovelace Dashboards → Resources → Click Plus button → Set Url as /local/humidifier-card.js → Set Resource type as JavaScript Module.<br>
Using YAML: Add the following code to lovelace section.<br>
resources:
  ```yaml
  - url: /local/humidifier-card.js/r/n
    type: module
  ```
Add custom:humidifier-card to Lovelace UI as any other card (using either editor or YAML configuration).

Typical example of using this card in YAML config would look like this:
  ```yaml
  - type: 'custom:humidifier-card'
    entity: fan.xiaomi_humidifier
    stats:
      - attribute: humidity
        unit: '%'
        subtitle: Влажность
      - attribute: temperature
        unit: '°C'
        subtitle: Температура
      - attribute: water_level
        unit: '%'
        subtitle: Уровень воды
    actions:
      - name: Низкая
        icon: 'mdi:weather-night'
        speed: Low
      - name: Средняя
        icon: 'mdi:circle-slice-4'
        speed: Mid
      - name: Высокая
        icon: 'mdi:circle-slice-7'
        speed: High
      - name: Auto
        icon: 'mdi:brightness-auto'
        speed: Auto
    show_name: true
    show_state: true
    show_toolbar: true
    compact_view: false
  ```
  
  Original card: <a href="https://github.com/dmitrybabeshko/homeassistant-purifier-card">dmitrybabeshko/homeassistant-purifier-card</a>
