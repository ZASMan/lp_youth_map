## Viewing the file locally

Look at the top right corner of this page, and click 'clone or download.' Click 'download zip.'

After downloading zip, open the folder, and find the file 'index.html'. Right click, and hit 'open with [your browser name]'.

## Installation

Open the file 'required_files'. You should see the following files:

**Note: This will assume that jquery is already loaded**

1. jquery-jvectormap-2.0.3.css
2. jquery-jvectormap.css
3. jqvmap.css
4. jquery.jvmap.js
5. jquery.vmap.world.js
6. youth_countries.js

Copy and paste the files into the appropriate folders. You can simply place them in your root directory, but its best practice to put them in a folder like 'cs' or 'js', respectively.

Add the stylesheets to your index.html as so:
```
    <link href="css/jquery-jvectormap-2.0.3.css" rel="stylesheet">
    <link href="css/jquery-jvectormap.css" rel="stylesheet">
    <link href="css/jqvmap.css" rel="stylesheet">
```

**Note: This assumes that your site has jquery loaded before these maps.**
And the javascripts as so:
```
    <!-- Jquery vmap and youth country records -->
    <script src="js/jquery.vmap.js"></script>
    <script src="js/jquery.vmap.world.js"></script>
    <script src="js/youth_countries.js"></script>
    <script>
        jQuery('#vmap').vectorMap({
        map: 'world_en',
        backgroundColor: null,
        color: '#ffffff',
        hoverOpacity: 0.7,
        selectedColor: '#666666',
        enableZoom: true,
        showTooltip: true,
        values: numberYouth,
        scaleColors: ['#ffffff', '#006491'],
        normalizeFunction: 'polynomial',
        onLabelShow: function (event, label, code) {
          label.append(': '+numberYouth[code]+' Youth');
        },            
        hoverOpacity: 0.7, // opacity for :hover
        rhoverColor: false
    });
    </script>
```

In the body of your HTML, add the following markup:
```
        <div class="col-lg-12 text-center">
          <p>Since 2005, we've worked with <strong> more than 3,500</strong> youth from <strong>117</strong> countries.</p>
           <div class="container">
          <div id="vmap" style="width: 800px; height: 600px"></div>
        </div>
```

If you look at the line of the script `jQuery('#vmap').vectormap`, you can see that it initializes on the div with the id vmap.


## Changing the statistics

Open the file at `vendor/youth_map/youth_countries.js`. You will see the countries listed as so:

```
var numberYouth = {
    "No Country": "204",
    "af": "11",
    "al": "2",
    "dz": "2",
    "ao": "2",
    "ag": "0",
    "ar": "16",
    "am": "0",
}
```


Simply change the numbers in statistics for each country acronym. Make sure they're in quotes and in the exact format to avoid syntax errors. You can view the country codes in the documentation [here](http://jvectormap.com/maps/world/world/).

That should handle it! Open issues with any questions.


## Jvector map
Credit to the *Jvector* map team for the awesome plugin!