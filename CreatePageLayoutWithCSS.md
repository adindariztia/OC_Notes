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

## Flexbox

* `flex-container`: container with items inside, arranged in rows or columns
* `flex-direction`: value varies between:
    - row
    - column
    - row-reverse (from right to left)
    - column-reverse (from bottom to top)
* `flex-box`: item arranged via flexbox
* `flex-wrap`, pilihan nilainya:
    - `wrap` : the flex items can take up multiple lines as needed, whether they're arranged in rows or columns
    - `nowrap`: the flex items cannot take up multiple lines. They'll all cram into either one row or column
    - `wrap-reverse`: the flex items can take up multiple lines as needed but are displayed in reverse
* Items in Flexbox are arranged horizontally or vertically depending on whether you specify row or column for your flex-direction. This "main" direction is what we call the flex items' main axis. The perpendicular direction is therefore the cross axis
    - If the elements are arranged horizontally in a row (or rows), the main axis is horizontal, and the cross axis is vertical
    - If the elements are arranged vertically in a column (or columns), the main axis is vertical, and the cross axis is horizontal
* alignment along main axis:
    - `flex-start`: aligned at the start of the container
    - `flex-end`: aligned at the end of the container
    - `center`: aligned in the center of the container
    - `space-between`: elements are spread out along the axis (there's space between each)
    - `space-around`: elements are spread out along the axis, but there's also space around the edges
    
    example:
    ```
    .container {
    display: flex;
    justify-content: space-around;
    }
    ```

    * alignment along cross axis:
        - `stretch`: the elements are stretched out along the whole cross axis (this is the default value)
        - `flex-start`: aligned at the start of the container
        - `flex-end`: aligned at the end of the container
        - `center` : aligned in the center of the container
        - `baseline`: aligned along the baseline of the container

        example:
        ```
        .container 
            { display: flex;
            justify-content: center;
            align-items: center;
            }
        ```
    * aligning one item, example:
        ```
        .container div:nth-child(6) {
            align-self: flex-end;
        }
        ```

    * `align-content` : to align multiple rows or columns along the cross-axis (value of this property similar to aligment along main axis)

    * visit [this chapter](https://openclassrooms.com/en/courses/5295881-create-web-page-layouts-with-css/5415181-align-items-and-justify-content) for detailed explanation and more examples. As you notice i'm getting lazier in taking notes i just copy-pasted them :(

    * `flex-basis`:control the space they take up along the container's main axis

    * `flex-grow`: to make elements bigger than the ones next to them
    * `flex-shrink`: to reduce the size of certain elements when there's not enough space
    * `flex`: combination of `flex-basis`, `flex-grow`, and `flex-shrink`

    example:

    ```
    .container div:nth-child(2) {
        flex: 1 3 100px;
    }
    ```

    This means the second element in the container will have a  flex-grow  of 1 (default), a  flex-shrink  of 3 (meaning it will shrink 3 times faster than the other elements), and a  flex-basis  of 100px (it's starting "width" if you will). 

    * revisiting [this chapter](https://openclassrooms.com/en/courses/5295881-create-web-page-layouts-with-css/5415656-adjust-element-dimensions) because why not

    * `order`: to reorder elements in your layout without touching the HTML, visit [this chapter](https://openclassrooms.com/en/courses/5295881-create-web-page-layouts-with-css/5419976-reorder-elements) for examples

    * PLEASE DO THE ACTIVITY [HERE](https://openclassrooms.com/en/courses/5295881-create-web-page-layouts-with-css/exercises/2766?to-redirect=true#/step1) (not yet started)

## Legacy Layouts

* `block-level` : elements start on new lines and take up the full width available to them

* `inline` : elements take up only as much space as they need and do not start on new lines

* `inline-block` : elements can display side-by-side but still can have width and height properties, which regular inline elements cannot

* Even without using Flexbox or CSS Grid, you can adjust where an element appears on a page by using a property called `position`

* `position` property values: 
    - `static`: element appears where it normally would in the flow of your HTML document
    - `relative`: position it relative to where it would normally be
    - `absolute` : Absolutely positioned elements are set relative to their nearest explicitly positioned ancestor
    - `fixed`: This is similar to absolute and relative positioning in that you have to set top, bottom, left, and right values. However, an element with a fixed position will scroll with the page and will often be positioned relative to the entire viewport, except in a very specific subset of cases

* read about float [here](https://openclassrooms.com/en/courses/5295881-create-web-page-layouts-with-css/5467706-float-elements)

* overlapping elements read [here](https://openclassrooms.com/en/courses/5295881-create-web-page-layouts-with-css/5467936-stack-elements-in-an-order)