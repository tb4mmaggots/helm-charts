# tb4mmaggots - Helm Charts!
## Usage

[Helm](https://helm.sh) must be installed to use the charts.  Please refer to
Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:

    $ helm repo add tb-helm https://tb4mmaggots.github.io/helm-charts

If you had already added this repo earlier, run `helm repo update` to retrieve
the latest versions of the packages.  You can then run `helm search repo
tb-helm` to see the charts.

To install the <chart-name> chart:

    $ helm install my-<chart-name> tb-helm/<chart-name>

To uninstall the chart:

    $ helm delete my-<chart-name>

## Charts:
{% comment %}[0] and [1] below represent key and value{% endcomment %}
{% for helm_chart in site.data.index.entries %}
{% assign title = helm_chart[0] | capitalize %}
{% assign all_charts = helm_chart[1] | sort: 'created' | reverse %}
{% assign latest_chart = all_charts[0] %}

<h3>
  {% if latest_chart.icon %}
  <img src="{{ latest_chart.icon }}" style="height:1.2em;vertical-align: text-top;" />
  {% endif %}
  {{ title }}
</h3>