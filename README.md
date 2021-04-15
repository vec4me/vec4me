<!--create a semi-random number using the last second of the send date-->
{% capture time_seed %}
  {{ 'now' | date: "%s" }}
{% endcapture %}

<!--manupulate using lots of maths-->
{% assign random = time_seed | times: 1103515245 | plus: 12345 | divided_by: 65536 | modulo: 32768 | modulo: 10 %}

<!--return number-->
{{ random }}
