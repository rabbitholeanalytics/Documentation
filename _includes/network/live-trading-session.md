<!-- TITLE AND DEFINITION starts -->

{% assign title = "Live Trading Session" %}
{% assign definition = site.data.network.live_trading_session %}
{% assign preposition = "a" %}
{% assign plural = "s" %}

<!--------------------------------------------- TITLE AND DEFINITION ends -->

{% if include.more == "yes" and include.heading == "more" %}
<details class='detailsCollapsible'><summary class='nobr'>Click to learn more about {{ title | downcase }}{{plural}}
</summary>
{% endif %}

{% if include.heading != "" and include.heading != "more" %}
{{include.heading}} {{title}}
{% endif %}

{% if include.icon != "no" %} 

{% if include.table == "yes" and include.icon != "no" %}
<table class='definitionTable'><tr><td>
{% endif %}

<img src='images/icons/{{include.icon}}{{ title | downcase | replace: " ", "-" }}.png' />

{% if include.table == "yes" and include.icon != "no" %}
</td><td>
{% endif %}

{% endif %}

{% if include.definition == "bold" %}
<strong>{{ definition }}</strong>
{% else %}
{% if include.definition != "no" %}
{{ definition }}
{% endif %}
{% endif %}

{% if include.table == "yes" and include.icon != "no" %}
</td></tr></table>
{% endif %}

{% if include.more == "yes" and include.content == "more" and include.heading != "more" %}
<details class='detailsCollapsible'><summary class='nobr'>Click to learn more about {{ title | downcase }}{{plural}}
</summary>
{% endif %}

{% if include.content != "no" %}

<!--------------------------------------------- CONTENT starts -->

A live trading session node must reference a trading system to gain access to the trading logic to be applied during the session. Other considerations framing the session come from the set of parameters attached to it.

{% include note.html content="Running a live trading session requires the setup of a key instance at the market reference. It also requires a live data feed, meaning that the corresponding sensor bot, along with all indicators used by the referenced trading system, must be up and running" %}

<!--------------------------------------------- CONTENT ends -->

{% endif %}

{% if include.more == "yes" and include.content != "more" and include.heading != "more" %}
<details class='detailsCollapsible'><summary class='nobr'>Click to learn more about {{ title | downcase }}{{plural}}
</summary>
{% endif %}

{% if include.adding != "" %}

{{include.adding}} Adding {{preposition}} {{title}} Node

<!--------------------------------------------- ADDING starts -->

To add a live trading session, select *Add Live Trading Session* on the trading process instance node menu. When a session is added, it is created with the full set of parameters.

{% include note.html content="After adding a session node, make sure you establish a reference to the trading system you want it to work with." %}

<!-- ADDING ends -->

{% endif %}

{% if include.configuring != "" %}

{{include.configuring}} Configuring the {{title}}

<!-- CONFIGURING starts -->

Select *Configure Session* on the menu to access the configuration.

```json
{
"folderName": "Session-Name"
}
```

* ```folderName``` allows you to set a significant name to the folder in which the data products&mdash;and logs&mdash;generated by the session are stored. If left blank, the system names the folders with the session id. This may be handy when you intend to consult the raw data generated by the session, as, otherwise, the folder would be hard to identify.

<!-- CONFIGURING ends -->

{% endif %}

{% if include.starting != "" %}

{{include.starting}} Starting {{preposition}} {{title}}

<!-- STARTING starts -->

Before you start a live trading session, the corresponding task needs to be running, as it is the task that puts the trading bot instance to run. Once the trading bot instance is running, select *Run* on the menu to start the session.

To stop a backtesting session, select *Stop* on the menu.

<!--------------------------------------------- STARTING ends -->

{% endif %}

{% if include.more == "yes" %}
</details>
{% endif %}