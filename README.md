# googlemaps
This project is creating a google maps of the Boston area of 3 locations using the Google maps API created using mostly Javascript.
<!DOCTYPE>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width", inital-scale=1.0>
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Google Maps API</title>
    <style>
        #map{
            height:400px;
            width:100%;
        }
    </style>
    </head>
<body>
    <h1>My Google Map</h1>
    <div id="map"></div>
    
    <script>
        function initMap(){
            //Map options
            var options = {
                zoom:8,
                center:{lat:42.3601,lng:-71.0589}
            }
            //New map
            var map = new google.maps.Map(document.getElementById('map'), options);
            
            /*
            //Add marker
            var marker = new google.maps.Marker({
                position:{lat:42.4668,lng:-70.9495},
                map:map,
                icon:'https://developers.google.com/maps/documentation/javascript/examples/full/images/beachflag.png'
            });
            
            var infoWindow= new google.maps.InfoWindow({
               content:'<h1>Lynn, MA</h1>' 
            });
            
            marker.addListener('click', function(){
               infoWindow.open(map, marker); 
            });
            */
            
            //Add array of markers
            var markers = [
             {
                coords:{lat:42.4668,lng:-70.9495},
                iconImage:'https://developers.google.com/maps/documentation/javascript/examples/full/images/beachflag.png',
                 content:'<h1>Lynn, MA</h1>'
            },
                
                {
                coords:{lat:42.3770,lng:-71.1167},
                content:'<h1>Cambridge, MA</h1>'    
                
                },
                
                {
                    coords:{lat:42.7762,lng:-71.0773},
                    content:'<h1>Amesbury, MA</h1>'
                    
                },
                
                {
                    coords:{lat:42.5778,lng:-70.7676},
                    content:'<h1>Manchester, MA</h1>'
                }
            ];
            
            //Loop through markers
            for(var i =0;i < markers.length;i++){
                addMarker(markers[i]);
            }
            
            
            
            
            
            //Add function for add marker
            function addMarker(props){
                var marker = new google.maps.Marker({
                position:props.coords,
                map:map,
                icon:props.iconImage,
                content:props.content    
            });
            }
        }
    
    </script>
    
     <script async defer
    src="https://maps.googleapis.com/maps/api/js?key=AIzaSyBPtDwtQKuzPOgHdSqh9uF1hXSqAGGBwOk&callback=initMap">
    </script>
    
    </body>





</html>
