# UFO Sightings with JavaScript

## Otherworldly Overview

### To create a website using ``HTML`` programming language that will allow its users to filter Unidentified Flying Object (UFO) sightings by the alleged sighting(s)' date, city, state, country, and shape. 

## Astral Analysis

### Searching For Sightings

Since our website would be handling five filters instead of just one, we first had to create a variable that could hold these filters as an object. 

    let filters = {};
 
After creating this variable, we use ``D3`` to listen for a user's ``"input"`` (i.e. entering search paramenters into one of or multiple of our website's UFO filters. 

    d3.selectAll("input").on("change", updateFilters) 

This event will listen for ``"changes"`` in a new function we will create; and we will save the element, the value, and the id that results from the filtering of the user's selected input.

    function updateFilters() {
    
      let changedElement = d3.select(this);
      
      let changedValue = changedElement.property("value")
      console.log(changedValue)
      
      let filterId = changedElement.attr("id")
      console.log(filterId)
 
We then create an ``If-Else`` statement to add searched for values and their accompanying ``filterID`` to the list the user was searching for; those not explicitly searched for are disregarded and dropped. 

      if (changedValue) {
        filters[filterId] = changedValue;
      }
      
      else {
        delete filters[filterId];
      }
      
Finally, we use our established function to create and display a new table containing our new filtered values. 

      filterTable();

### Ultizing Search Functions

## Celestial Summary 

###
