# dashing-radarchart

## Preview

![RadarChart](https://raw.githubusercontent.com/wiki/jorgemorgado/dashing-radarchart/radarchart.png)

## Description

Simple [Dashing](http://shopify.github.com/dashing) widget (and associated job)
to render radar charts. Uses [Chart.js](http://www.chartjs.org/) library.

## Dependencies

Download `Chart.min.js` from [http://www.chartjs.org](http://www.chartjs.org)
and copy it into `assets/javascripts`.

## Usage

Add the following code on the desired dashboard:

```erb
<li data-row="1" data-col="2" data-sizex="1" data-sizey="1">
  <div data-id="radarchart" data-view ="RadarChart" data-title="Radar Chart" data-moreinfo=""></div>
</li>
```

Create your radar chart job `my_radarchart_job.rb`:

```ruby
# Note: change this to obtain your chart data from some external source
labels = ['January', 'February', 'March', 'April', 'May', 'June', 'July']
data = [
  {
    label: 'My First dataset',
    fillColor: 'rgba(220,220,220,0.5)',
    strokeColor: 'rgba(220,220,220,0.8)',
    highlightFill: 'rgba(220,220,220,0.75)',
    highlightStroke: 'rgba(220,220,220,1)',
    data: Array.new(labels.length) { rand(40..80) },
  }, {
    label: 'My Second dataset',
    fillColor: 'rgba(151,187,205,0.5)',
    strokeColor: 'rgba(151,187,205,0.8)',
    highlightFill: 'rgba(151,187,205,0.75)',
    highlightStroke: 'rgba(151,187,205,1)',
    data: Array.new(labels.length) { rand(40..80) },
  }
]

send_event('radarchart', { labels: labels, datasets: data })
```

## Contributors

- [Jorge Morgado](https://github.com/jorgemorgado)

## License

This widget is released under the [MIT License](http://www.opensource.org/licenses/MIT).
