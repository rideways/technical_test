# Supplier API Documentation

This is the API specification for the BookingGo technical test.

## Accessing the API of a supplier

The api can be accessed via the URL `https://techtest.rideway.com/{supplier_id}`

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
            "supplier_id": "Dave",
            "pickup": "51.470020,-0.454295",
            "dropoff": "51.00000,1.0000",
            options: [
                {
                    "car_type": "STANDARD",
                    "price": 10001
                },
                {
                    "car_type": "EXECUTIVE",
                    "price": 20000
                },
                {
                    "car_type": "LUXURY",
                    "price": 30000
                }
            ]
        }
        
### Client Error
* http status code 400


        {
            "error_code": 121,
            "error_reason": "Incorrect parameters"
        }

### Server Error
* http status code 500

        {
            "error_code": 1212,
            "error_reason": "Something has gone wrong"
        }
