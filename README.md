# Movie Theaters per 100k People by State (2023)


By Joshua Turner

## Purpose

This map shows how many movie theaters each state has for every 100,000 people in 2023. I used theaters per 100k instead of just the total number of theaters because big states like California would have the most theaters just because they have more people. This way you can compare states fairly.

The states with the most theaters per person are mostly rural states in the middle of the country like Wyoming, the Dakotas and Montana. The states with the fewest are mostly in the South, like South Carolina and Alabama, plus New Jersey.

## Data

- Number of theaters: Census County Business Patterns 2023, (movie theaters, not counting drive-ins)
- Population: Census ACS 2023 1-Year estimates
- State shapes: Census cb_2023_us_state_20m

To get theaters per 100k I did theaters / population x 100,000. Then I joined the data to the state shapes in mapshaper and exported it as theaters.geojson. It has all 50 states and DC.

## Symbolization

I used a choropleth map with 5 classes:

- Less than 1.0
- 1.0 - 1.3
- 1.3 - 1.6
- 1.6 - 2.5
- 2.5 and up

I picked these numbers so each class has a decent amount of states in it and the legend is easy to read. For colors I used the Blues color scheme from ColorBrewer. Light blue means fewer theaters per person and dark blue means more. I used one color going from light to dark because the data just goes from low to high.

## Design

I made the background plain dark gray with no base-map so the states stand out. I made the state borders light gray so the dark blue states don't blend into the background.

On a normal web map Alaska looks huge because it's so far north, so I moved Alaska and Hawaii down below the lower 48 and resized them. This way the whole country fits on the screen and the lower 48 aren't tiny.

The map has:

- a title box in the top left with the title, a short description, my name and the data sources
- an info box in the top right that shows the state name and number when you hover over a state
- a popup when you click a state that shows the number of theaters, population and theaters per 100k
- a legend in the bottom right

I used Leaflet, leaflet-ajax, chroma.js and jQuery.
