HTML Layout: The HTML layout defines the element structure that would be shown on the page. This includes:

- Header: This will contain the application title and buttons for saving the modified image or resetting the filters.
  
-  Image Preview: This section will hold the canvas that we will be working on. It will help to preview the image as we are changing the filter values.
-  Filter Sliders: This section will have all the sliders that will handle the image filter values.
-  Preset Filters: This section contains a set of buttons that can be used for setting multiple values at once for achieving a particular style.
-  File Controls Area: This section contains a button for selecting a new image from the file system.

CSS Styling: 

We will make some minor changes along with the default Materialize styles according to our applications. The main changes include:

-  Hiding the image filter sliders and buttons when an image has not been selected and showing a help message instead using the display property.
-  Centering the Image Preview by using the flex and justify-content properties.
-  Setting the maximum height of the canvas to a fixed value and using the object-fit property to make sure that it fits in the given area. This will help to use the application on all screen sizes without the image occupying too much space.

-  
