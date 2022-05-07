# UFO Sightings with JavaScript

## Otherworldly Overview

### To create a website using ``HTML`` programming language that will allow its users to filter Unidentified Flying Object (UFO) sightings by the alleged sighting(s)' city, state, country, and shape. These search paremeters will be additional tool in narrowing down these sighting along with the website's previous date-based search functionality.

## Astral Analysis

### Creating A Working Search Filter

* HTML File

First, we had to update our ``index.html`` file  with our new search parameters: city, state, country, and shape.              
                
                    </li>
                      <li class="list-group-item bg-dark">
                        <label for="city">Enter City</label>
                        <input type="text" placeholder="clinton" id="city" />
                    </li>   
                    
                    <li class="list-group-item bg-dark">
                      <label for="state">Enter State</label>
                      <input type="state" placeholder="nj" id="state" />
                    </li>    
                    
                    <li class="list-group-item bg-dark">
                      <label for="country">Enter Country</label>
                      <input type="country" placeholder="us" id="country" />
                    </li>  
                    
                    <li class="list-group-item bg-dark">
                      <label for="date">Enter Shape</label>
                      <input type="shape" placeholder="cigar" id="shape" />
                    </li>  

* Java Script File

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

### Searching for Sightings

With this new functionality a user can now search on this website by simply typing in their search parameter within one of the specified search bars on the right-hand side of the website. When the user either clicks away from the search bar or presses the ``Enter`` key, the website will filter for the specified parameters and display all matches. 

#### Without Search Filters

![Deliverable](https://github.com/chrisknox97/ufos/blob/main/PNGs/without_search.png)

#### With One Search Filter

* Search Based On Shape

![Deliverable](https://github.com/chrisknox97/ufos/blob/main/PNGs/shape_search.png)

* Search Based on State

![Deliverable](https://github.com/chrisknox97/ufos/blob/main/PNGs/state_search.png)

#### With Multiple Search Filters

* Search Based on 5 Filters

![Deliverable](https://github.com/chrisknox97/ufos/blob/main/PNGs/multi_search.png)

* Search Based on 4 Filters

![Deliverable](https://github.com/chrisknox97/ufos/blob/main/PNGs/multi_search_2.png)

## Celestial Summary 

###
