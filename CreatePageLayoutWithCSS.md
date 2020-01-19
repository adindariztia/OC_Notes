# Create Page Layout With CSS

## CSS Grid
* `display: grid` to set css display as grid

* `grid-template-columns` set the number of column in grid and width
    > `grid-template-columns: 20% 20% 20%`
    >: creates 3 columns with 20% width

* `grid-template-rows` set the number of rows in grid and its height
    >  `grid-template-rows: 2em 2em 2em`: creates 3 rows with 2em height

* `grid-auto-rows`: set to be defined rows to certain height
    > `grid-auto-rows: 200px`: set to be defined rows to have 200px height

* `grid-gap` create gaps between grid
* `grid-template` defined rows and columns of grid in a shorthand way
    > `grid-template: repeat(3, 1.6em) / repeat(3, 1fr)` creates 3 rows, height: 1.6em and 3 columns, width 1 fr
* creates __*merged grid*__ using these properties: 
    - `grid-column-start`
    - `grid-column-end`
    - `grid-row-start`
    -  `grid-row-end`
    
    For examples visit [this OC chapter](https://openclassrooms.com/en/courses/5295881-create-web-page-layouts-with-css/5364131-define-grid-element-height-and-widthhttps://openclassrooms.com/en/courses/5295881-create-web-page-layouts-with-css/5364131-define-grid-element-height-and-width)

* example of grid area usage:
    ```.container {
    display: grid;
    grid-template: repeat(3, 1fr) / repeat(4, 1fr);
    grid-template-areas: 
        "h h h h"
        "a a b b"
        "f f f f"
        ;
    }
    ```


    set grid area:
    ```
    header {
    grid-area: h;
    }
    ```

* set responsive layout without using media queries, click [this chapter](https://openclassrooms.com/en/courses/5295881-create-web-page-layouts-with-css/5369951-set-columns-depending-on-screen-size)
* exercise: Calendar, [click here](https://codepen.io/adindariztia/pen/MWYzYrW)