  # A little fun with Fabric Real-Time Analytics!
The Kusto engine inside Fabric Real-Time Analytics is the same powerful analytics engine you've grown to love over the years. I figured it would be nice to dust off one of our geospatial capabilities demo originally done by my colleague Michael Brichko and add a little twist!
What you will need to run this:
- 1 x Fabric enabled workspace
- 1 x KQL database (to run the code against)
- 1 x KQL query set (to execute the code)
- 1/2 cup of sugar
- 1/2 cup of rolled oats (wait wrong recipe! moving on...)

Ok, now on to the fun part!

Checking that you are connected to a KQL db
Head over to your KQL query set and make sure you are connected to a KQL database by looking to the left
Now go ahead and copy&paste the code snippet below to your KQL query set.

``` Kusto
let MyMysteryShape = dynamic({"type":"Polygon","coordinates":[[[-15.90661,-67.32941],[-16.19984,-67.34552],[-16.49293,-67.36219],[-16.78602,-67.37885],[-17.07911,-67.3955],[-17.3722,-67.41214],[-17.66529,-67.42876],[-17.95837,-67.44538],[-18.25146,-67.46198],[-18.54455,-67.47857],[-18.83764,-67.49515],[-19.13073,-67.51172],[-19.42382,-67.52827],[-19.71691,-67.54482],[-20.01,-67.56135],[-20.30308,-67.57787],[-20.59617,-67.59438],[-20.88926,-67.61088],[-21.18235,-67.62737],[-21.47544,-67.64384],[-21.76853,-67.66031],[-22.06162,-67.67676],[-22.35468,-67.69327],[-22.64144,-67.721],[-22.91219,-67.76623],[-23.15953,-67.82763],[-23.37674,-67.90336],[-23.55787,-67.99123],[-23.69789,-68.08872],[-23.79338,-68.19302],[-23.87134,-68.29896],[-23.9493,-68.4044],[-24.02726,-68.50936],[-24.10522,-68.61383],[-24.18318,-68.71782],[-24.26114,-68.82132],[-24.3391,-68.92434],[-24.41706,-69.02689],[-24.49502,-69.12896],[-24.57298,-69.23055],[-24.65094,-69.33167],[-24.7289,-69.43232],[-24.80685,-69.53251],[-24.88481,-69.63222],[-24.96277,-69.73147],[-25.04073,-69.83025],[-25.11869,-69.92858],[-25.19665,-70.02644],[-25.27461,-70.12385],[-25.35257,-70.2208],[-25.41934,-70.30573],[-25.45252,-70.40451],[-25.41959,-70.50283],[-25.32537,-70.59617],[-25.17415,-70.68042],[-24.97299,-70.752],[-24.73082,-70.80787],[-24.45828,-70.84556],[-24.16782,-70.86394],[-23.8721,-70.86839],[-23.57693,-70.86064],[-23.2835,-70.84723],[-22.99004,-70.83386],[-22.69658,-70.82049],[-22.40313,-70.80711],[-22.12474,-70.77579],[-21.90698,-70.71053],[-21.78442,-70.62193],[-21.70693,-70.52683],[-21.62945,-70.43128],[-21.55196,-70.33527],[-21.47448,-70.23882],[-21.39699,-70.14191],[-21.3195,-70.04454],[-21.24202,-69.94672],[-21.06414,-69.88725],[-20.77113,-69.87216],[-20.47813,-69.85707],[-20.18506,-69.8421],[-19.89192,-69.82729],[-19.59879,-69.81246],[-19.31517,-69.78623],[-19.13403,-69.7077],[-19.05536,-69.60841],[-18.97726,-69.5086],[-18.89917,-69.40832],[-18.82107,-69.30757],[-18.74297,-69.20635],[-18.66487,-69.10465],[-18.58678,-69.00248],[-18.50868,-68.89984],[-18.3964,-68.81066],[-18.10329,-68.79507],[-17.81017,-68.77947],[-17.51705,-68.76385],[-17.22394,-68.74823],[-16.9358,-68.73091],[-16.64285,-68.71487],[-16.39154,-68.66267],[-16.28276,-68.56325],[-16.20484,-68.45854],[-16.12693,-68.35334],[-16.04902,-68.24765],[-15.97111,-68.14148],[-15.89319,-68.03481],[-15.81528,-67.92764],[-15.73737,-67.81998],[-15.65946,-67.71182],[-15.58154,-67.60316],[-15.51026,-67.49347],[-15.59413,-67.38722],[-15.84422,-67.33117],[-15.90661,-67.32941]]]});
let MyMysteryShapeCutout = dynamic({"type":"MultiPolygon","coordinates":[[[[-22.58586,-70.60894],[-22.87933,-70.62243],[-23.1728,-70.63591],[-23.46627,-70.64938],[-23.76007,-70.66188],[-24.05596,-70.66221],[-24.34426,-70.64167],[-24.59104,-70.58833],[-24.76042,-70.50811],[-24.82815,-70.41226],[-24.78354,-70.3145],[-24.65785,-70.22411],[-24.46896,-70.14722],[-24.22436,-70.09084],[-23.95119,-70.052],[-23.66568,-70.02513],[-23.37485,-70.006],[-23.08181,-69.99107],[-22.78877,-69.97613],[-22.49574,-69.96118],[-22.20269,-69.94623],[-21.90966,-69.93126],[-21.93604,-70.01367],[-22.01337,-70.11119],[-22.09071,-70.20826],[-22.16805,-70.30487],[-22.24538,-70.40103],[-22.32272,-70.49674],[-22.58586,-70.60894]]],[[[-19.61853,-69.50513],[-19.79486,-69.58642],[-20.071,-69.62019],[-20.36419,-69.63504],[-20.65737,-69.64987],[-20.9505,-69.66482],[-21.24358,-69.67989],[-21.53665,-69.69495],[-21.82973,-69.71],[-22.12281,-69.72504],[-22.41588,-69.74007],[-22.70896,-69.75509],[-23.00204,-69.77009],[-23.29511,-69.78509],[-23.58819,-69.80007],[-23.88126,-69.81505],[-24.17196,-69.83461],[-24.41683,-69.84727],[-24.33875,-69.74858],[-24.26068,-69.64942],[-24.18261,-69.5498],[-24.10765,-69.4495],[-24.09548,-69.43857],[-24.00333,-69.3395],[-23.86721,-69.24671],[-23.6653,-69.17029],[-23.41289,-69.1155],[-23.13637,-69.0778],[-22.84955,-69.05141],[-22.55793,-69.03288],[-22.26483,-69.01742],[-21.97172,-69.00196],[-21.67862,-68.98648],[-21.38551,-68.97099],[-21.0924,-68.95549],[-20.79929,-68.93998],[-20.50619,-68.92446],[-20.21308,-68.90893],[-19.91997,-68.89339],[-19.62686,-68.87784],[-19.33376,-68.86227],[-19.13712,-68.87758],[-19.21473,-68.98038],[-19.29234,-69.0827],[-19.36995,-69.18454],[-19.44756,-69.28591],[-19.52517,-69.3868],[-19.60278,-69.48723],[-19.61853,-69.50513]]],[[[-17.15852,-68.51561],[-17.45155,-68.53162],[-17.74462,-68.54751],[-18.03771,-68.56334],[-18.33079,-68.57916],[-18.62388,-68.59497],[-18.91697,-68.61077],[-19.21006,-68.62656],[-19.50315,-68.64233],[-19.79624,-68.6581],[-20.08932,-68.67385],[-20.38241,-68.6896],[-20.6755,-68.70533],[-20.96858,-68.72105],[-21.26168,-68.73676],[-21.55476,-68.75246],[-21.84785,-68.76815],[-22.14094,-68.78383],[-22.43402,-68.79949],[-22.72712,-68.81515],[-23.0202,-68.83079],[-23.31217,-68.84876],[-23.59976,-68.87432],[-23.60086,-68.80097],[-23.52218,-68.69744],[-23.44349,-68.59343],[-23.3648,-68.48894],[-23.28612,-68.38396],[-23.20861,-68.27838],[-23.11608,-68.17416],[-22.95989,-68.08071],[-22.74581,-68.00457],[-22.48752,-67.95076],[-22.20148,-67.92293],[-21.90839,-67.90665],[-21.61529,-67.89037],[-21.32221,-67.87407],[-21.02912,-67.85775],[-20.73603,-67.84143],[-20.44294,-67.8251],[-20.14985,-67.80875],[-19.85676,-67.79239],[-19.56367,-67.77602],[-19.27058,-67.75964],[-18.97749,-67.74325],[-18.6844,-67.72685],[-18.39131,-67.71043],[-18.09822,-67.69401],[-17.80513,-67.67757],[-17.51204,-67.66112],[-17.21895,-67.64466],[-16.92586,-67.62818],[-16.63277,-67.6117],[-16.33968,-67.59521],[-16.25021,-67.64747],[-16.32823,-67.75592],[-16.40624,-67.86386],[-16.48426,-67.97131],[-16.56228,-68.07826],[-16.6403,-68.18472],[-16.71832,-68.29069],[-16.79633,-68.39616],[-17.15852,-68.51561]]]]});
range i from 1 to 3000000 step 1 
| project   
            Longitude = (rand() * -100)
          , Latitude =  (rand() * -100)
| where    geo_point_in_polygon(Longitude, Latitude, MyMysteryShape)
  and not (geo_point_in_polygon(Longitude, Latitude, MyMysteryShapeCutout))
| extend val = rand(6)
| render scatterchart with (kind = map, legend = hidden)
```

Go ahead and run this... pretty cool uh! Let's break down what's happening here line by line. Because KQL is so awesome, there's only 10 lines to go through here :)
## Lines 1 and 2
``` Kusto
let MyMysteryShape = dynamic({"type":"Polygon","coordinates":[[[-15.90661,-67.32941],[-16.19984,-67.34552],[-16.49293,-67.36219],[-16.78602,-67.37885],[-17.07911,-67.3955],[-17.3722,-67.41214],[-17.66529,-67.42876],[-17.95837,-67.44538],[-18.25146,-67.46198],[-18.54455,-67.47857],[-18.83764,-67.49515],[-19.13073,-67.51172],[-19.42382,-67.52827],[-19.71691,-67.54482],[-20.01,-67.56135],[-20.30308,-67.57787],[-20.59617,-67.59438],[-20.88926,-67.61088],[-21.18235,-67.62737],[-21.47544,-67.64384],[-21.76853,-67.66031],[-22.06162,-67.67676],[-22.35468,-67.69327],[-22.64144,-67.721],[-22.91219,-67.76623],[-23.15953,-67.82763],[-23.37674,-67.90336],[-23.55787,-67.99123],[-23.69789,-68.08872],[-23.79338,-68.19302],[-23.87134,-68.29896],[-23.9493,-68.4044],[-24.02726,-68.50936],[-24.10522,-68.61383],[-24.18318,-68.71782],[-24.26114,-68.82132],[-24.3391,-68.92434],[-24.41706,-69.02689],[-24.49502,-69.12896],[-24.57298,-69.23055],[-24.65094,-69.33167],[-24.7289,-69.43232],[-24.80685,-69.53251],[-24.88481,-69.63222],[-24.96277,-69.73147],[-25.04073,-69.83025],[-25.11869,-69.92858],[-25.19665,-70.02644],[-25.27461,-70.12385],[-25.35257,-70.2208],[-25.41934,-70.30573],[-25.45252,-70.40451],[-25.41959,-70.50283],[-25.32537,-70.59617],[-25.17415,-70.68042],[-24.97299,-70.752],[-24.73082,-70.80787],[-24.45828,-70.84556],[-24.16782,-70.86394],[-23.8721,-70.86839],[-23.57693,-70.86064],[-23.2835,-70.84723],[-22.99004,-70.83386],[-22.69658,-70.82049],[-22.40313,-70.80711],[-22.12474,-70.77579],[-21.90698,-70.71053],[-21.78442,-70.62193],[-21.70693,-70.52683],[-21.62945,-70.43128],[-21.55196,-70.33527],[-21.47448,-70.23882],[-21.39699,-70.14191],[-21.3195,-70.04454],[-21.24202,-69.94672],[-21.06414,-69.88725],[-20.77113,-69.87216],[-20.47813,-69.85707],[-20.18506,-69.8421],[-19.89192,-69.82729],[-19.59879,-69.81246],[-19.31517,-69.78623],[-19.13403,-69.7077],[-19.05536,-69.60841],[-18.97726,-69.5086],[-18.89917,-69.40832],[-18.82107,-69.30757],[-18.74297,-69.20635],[-18.66487,-69.10465],[-18.58678,-69.00248],[-18.50868,-68.89984],[-18.3964,-68.81066],[-18.10329,-68.79507],[-17.81017,-68.77947],[-17.51705,-68.76385],[-17.22394,-68.74823],[-16.9358,-68.73091],[-16.64285,-68.71487],[-16.39154,-68.66267],[-16.28276,-68.56325],[-16.20484,-68.45854],[-16.12693,-68.35334],[-16.04902,-68.24765],[-15.97111,-68.14148],[-15.89319,-68.03481],[-15.81528,-67.92764],[-15.73737,-67.81998],[-15.65946,-67.71182],[-15.58154,-67.60316],[-15.51026,-67.49347],[-15.59413,-67.38722],[-15.84422,-67.33117],[-15.90661,-67.32941]]]});
let MyMysteryShapeCutout = dynamic({"type":"MultiPolygon","coordinates":[[[[-22.58586,-70.60894],[-22.87933,-70.62243],[-23.1728,-70.63591],[-23.46627,-70.64938],[-23.76007,-70.66188],[-24.05596,-70.66221],[-24.34426,-70.64167],[-24.59104,-70.58833],[-24.76042,-70.50811],[-24.82815,-70.41226],[-24.78354,-70.3145],[-24.65785,-70.22411],[-24.46896,-70.14722],[-24.22436,-70.09084],[-23.95119,-70.052],[-23.66568,-70.02513],[-23.37485,-70.006],[-23.08181,-69.99107],[-22.78877,-69.97613],[-22.49574,-69.96118],[-22.20269,-69.94623],[-21.90966,-69.93126],[-21.93604,-70.01367],[-22.01337,-70.11119],[-22.09071,-70.20826],[-22.16805,-70.30487],[-22.24538,-70.40103],[-22.32272,-70.49674],[-22.58586,-70.60894]]],[[[-19.61853,-69.50513],[-19.79486,-69.58642],[-20.071,-69.62019],[-20.36419,-69.63504],[-20.65737,-69.64987],[-20.9505,-69.66482],[-21.24358,-69.67989],[-21.53665,-69.69495],[-21.82973,-69.71],[-22.12281,-69.72504],[-22.41588,-69.74007],[-22.70896,-69.75509],[-23.00204,-69.77009],[-23.29511,-69.78509],[-23.58819,-69.80007],[-23.88126,-69.81505],[-24.17196,-69.83461],[-24.41683,-69.84727],[-24.33875,-69.74858],[-24.26068,-69.64942],[-24.18261,-69.5498],[-24.10765,-69.4495],[-24.09548,-69.43857],[-24.00333,-69.3395],[-23.86721,-69.24671],[-23.6653,-69.17029],[-23.41289,-69.1155],[-23.13637,-69.0778],[-22.84955,-69.05141],[-22.55793,-69.03288],[-22.26483,-69.01742],[-21.97172,-69.00196],[-21.67862,-68.98648],[-21.38551,-68.97099],[-21.0924,-68.95549],[-20.79929,-68.93998],[-20.50619,-68.92446],[-20.21308,-68.90893],[-19.91997,-68.89339],[-19.62686,-68.87784],[-19.33376,-68.86227],[-19.13712,-68.87758],[-19.21473,-68.98038],[-19.29234,-69.0827],[-19.36995,-69.18454],[-19.44756,-69.28591],[-19.52517,-69.3868],[-19.60278,-69.48723],[-19.61853,-69.50513]]],[[[-17.15852,-68.51561],[-17.45155,-68.53162],[-17.74462,-68.54751],[-18.03771,-68.56334],[-18.33079,-68.57916],[-18.62388,-68.59497],[-18.91697,-68.61077],[-19.21006,-68.62656],[-19.50315,-68.64233],[-19.79624,-68.6581],[-20.08932,-68.67385],[-20.38241,-68.6896],[-20.6755,-68.70533],[-20.96858,-68.72105],[-21.26168,-68.73676],[-21.55476,-68.75246],[-21.84785,-68.76815],[-22.14094,-68.78383],[-22.43402,-68.79949],[-22.72712,-68.81515],[-23.0202,-68.83079],[-23.31217,-68.84876],[-23.59976,-68.87432],[-23.60086,-68.80097],[-23.52218,-68.69744],[-23.44349,-68.59343],[-23.3648,-68.48894],[-23.28612,-68.38396],[-23.20861,-68.27838],[-23.11608,-68.17416],[-22.95989,-68.08071],[-22.74581,-68.00457],[-22.48752,-67.95076],[-22.20148,-67.92293],[-21.90839,-67.90665],[-21.61529,-67.89037],[-21.32221,-67.87407],[-21.02912,-67.85775],[-20.73603,-67.84143],[-20.44294,-67.8251],[-20.14985,-67.80875],[-19.85676,-67.79239],[-19.56367,-67.77602],[-19.27058,-67.75964],[-18.97749,-67.74325],[-18.6844,-67.72685],[-18.39131,-67.71043],[-18.09822,-67.69401],[-17.80513,-67.67757],[-17.51204,-67.66112],[-17.21895,-67.64466],[-16.92586,-67.62818],[-16.63277,-67.6117],[-16.33968,-67.59521],[-16.25021,-67.64747],[-16.32823,-67.75592],[-16.40624,-67.86386],[-16.48426,-67.97131],[-16.56228,-68.07826],[-16.6403,-68.18472],[-16.71832,-68.29069],[-16.79633,-68.39616],[-17.15852,-68.51561]]]]});
```
These are used to create two scalar variable called "MyMysteryShape" and "MyMysteryShapeCutout" respectively. Both are created as DYNAMIC types and contain a valid GeoJSON polygon definition. In other words some shape, somewhere on earth!
## Line 3

``` Kusto
range i from 1 to 3000000 step 1 
```
use the range() operator to allows us to generate a set of rows based on a start and end condition. Think of this a a "while" loop. Here we are asking it to generate 3 Million rows. 
## Lines 4, 5 and 6
``` Kusto
| project  
            Longitude = (rand() * -100)
          , Latitude =  (rand() * -100) 
```
These are a prettified project statement that will create two new columns to go along with the 3 million rows we're generating on line 3 (remember KQL is sequential). But what are we projecting? we're essentially creating random longitudes and latitudes by using a random number between 0 and 1 using the rand() function and we are multiplying it by negative one hundred (-100). The reason is we want all of our randomly generated coordinates to be west of the prime meridian and south of the equator (in non pirate parlance: a negative longitude and latitude).
## Lines 7 and 8
``` Kusto
| where    geo_point_in_polygon(Longitude, Latitude, MyMysteryShape
  and not (geo_point_in_polygon(Longitude, Latitude, MyMysteryShapeCutout)))
``` 
##Line 9
``` Kusto
| extend val = rand(6)
```
We're now creating a new column to simulate a "value" using our trusted rand() function. This is adding some randomness so we have pretty colors in the end result :)
## Line 10
``` Kusto
| render scatterchart with (kind = map, legend = hidden)
```
We bring it home with a render command to show the remaining coordinates on a map using a scatterchart of type "map".
** Nerd alert **
The image you see is placed all the way near Antarctica for a few reasons:
- There's plenty of ocean there, making for a nice "canvas"
- The Mercator projection that allows us to "flatten" the earth in 2D makes it a bit easier to draw in the extremely high latitudes. Things get a bit more squished near the equator.

That's it folks, Hope you enjoyed this nugget of KQL fun and we'll be back soon with even cooler stuff!