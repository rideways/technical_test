# Supplier API Documentation

This is the API specification for the BookingGo technical test.

## Accessing the API of a supplier

The api can be accessed via the URL `https://techtest.rideways.com/{supplier_id}/`

Valid supplier ids are `dave`, `eric`, `jeff`

## Query Parameters

The Supplier API takes the following query parameters:
        
+ pickup
    - Pickup location for the journey
    - lat, long e.g `3.410632,-2.157533`

+ dropoff
    - Drop off location for the journey
    - lat, long e.g `3.410632,-2.157533`
      
## Responses

### Successful Query

* http status code 200

        {
            "supplier_id": "DAVE",
            "pickup": "51.470020,-0.454295",
            "dropoff": "51.00000,1.0000",
            "options": [
                {
                    "car_type": "STANDARD",
                    "price": 671808
                },
                {
                    "car_type": "EXECUTIVE",
                    "price": 375545
                },
                {
                    "car_type": "LUXURY",
                    "price": 583438
                },
                {
                    "car_type": "MINIBUS",
                    "price": 37456
                }
            ]
        }
        
### Client Error
* http status code 400


        {
            "timestamp": "2018-08-14T13:11:34.937+0000",
            "status": 400,
            "error": "Bad Request",
            "message": "Required String parameter 'pickup' is not present",
            "path": "/dave"
        }

### Server Error
* http status code 500

        {
            "timestamp": "2018-08-14T13:12:34.072+0000",
            "status": 500,
            "error": "Internal Server Error",
            "message": "Something has gone wrong",
            "path": "/dave"
        }
