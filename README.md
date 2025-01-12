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

JavaScript Section: 

The section contains the main logic of the application. Here, we will divide the logic into 5 steps, which are described below:

Step 1: Defining the variables and creating a reference to the HTML elements:

We will first select all the elements that need to be modified by JavaScript using the querySelector() method. They are then assigned variable names so that they could be accessed easily. A reference to the canvas and its 2D context is also created for drawing the image.

Step 2: Loading an image from the file system:

- We will use the invisible <img> element, which we have defined in the HTML as the source image before drawing it to the canvas.
  
- In the uploadImage() function, we will first load the image using the URL.createObjectURL() method and assign it to the src property of the above-mentioned source image element. The image file can be accessed using event.target.files[0] from the change event of the file selector.
  
- We will then set the height and width of the canvas to be equal to the image’s dimensions. We will also set the crossOrigin property to anonymous to prevent the tainted canvas problem. We will then call the applyFilter() function for drawing the image to canvas. This function is explained in the next step.
  
- We will also make the image controls visible and hide the help text that was displayed earlier.

Step 3: Drawing the image and applying the current filter values.

- The applyFilter() function: This is the main function that handles the drawing of the image and applying the filter values. The Canvas API has a filter property that applies filters to the canvas. As the property can only be assigned once, we will have to specify all the filters at the same time so that they get applied together.

-  We will start by creating the string that will contain the filters we have chosen for this application. These are the common filters that are available in CSS. We will get the current values of the sliders using the value property and use it in the string at the correct places.

-  We will then assign this string to the filter property of the canvas. This will assign apply the filters to the canvas.
  
-  Finally, we will draw the image using the drawImage() method of the Context API.

Step 4: Using preset filters for the image:

-  Each of the preset filter buttons we have defined above can be used to set a certain value for each of the sliders. This will apply a unique combination of values that can be used for quickly achieving a look and then further modifying the values as needed.
  
-  Each of the functions will first reset the image by using the resetImage() function we will define in the next step, then set the required filter values for that preset and then call applyFilter() for redrawing the image with the filters.

-  The user can then change the sliders after the preset has been applied for further changing the look of the filter.

Step 5: Resetting and Saving the image:

- Reset Image: The image can be reset by setting the filter values to their default values and then calling the applyFilter() method to redraw the original image. This will also adjust the sliders to their default positions.
  
- Saving Image: The image can be saved by referring to the temporary <a> element we have created in the HTML section. We will use the download property for setting the name of the file and the href property for setting the canvas data to be saved. We will convert the canvas to a data URL using the toDataURL() method and then to an image stream so that it starts downloading automatically.
