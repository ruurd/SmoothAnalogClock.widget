# Smooth Analog Clock for [Übersicht](tracesof.net/uebersicht/)
An analog clock with smooth running pointers for [Übersicht](tracesof.net/uebersicht/) (that is also reasonably efficient, see below)
![screenshot](https://cloud.githubusercontent.com/assets/17210173/20464803/fe62ce80-af4e-11e6-80d6-d5c0890f8ef1.png)
## Configuration
At the top of the index.coffee file is a section with styling options, the default options are as follows:
```coffeescript
options =
  pos:
    x: "left: 40px"
    y: "top: 40px"
  size: 512 # width of the clock in px
  scale: 1  # for retina displays set to 2
  fontSize: 48   # in px
  secPtr:
    color: "rgb(239,53,114)" # css color string
    width: 3     # in px
    length: 230  # in px
  minPtr:
    color: "rgb(107,191,221)" # css color string
    width: 10     # in px
    length: 184   # in px
  hrPtr:
    color: "rgb(106,147,211)" # css color string
    width: 10     # in px
    length: 128   # in px
  markerOffset: 4 # offset from the border of the clock in px
  majorMarker:
    width: 2      # in px
    length: 60    # in px
  minorMarker:
    width: 2      # in px
    length: 40    # in px
  intervalLength: 30  # interval between the transition triggers in seconds (also change the refresh rate)
  backgroundBlur: false
```
## Bugs
If any bugs appear please file an issue, I will then see if I can fix them.
### Known Bugs
+ The background blur filter of the clock is not clipped properly

### Contributors
Thanks to [@ruurd](https://github.com/ruurd) who discovered a bug in how the current time of day in seconds was computed
and suggested code to fix [the issue](https://github.com/N00bySumairu/SmoothAnalogClock.widget/issues/2).

## Notes
This clock works by using css transitions of the transform property of the pointers. Transitions of the transform property are hardware accelerated, this allows the clock to be reasonably efficient while also having silky smooth 60fps animations (best case).  
Since tests using different transition trigger intervals other than 30s have yet to be made, the clock might not work as expected using a different interval.  
