![logo](logo.png)

# BookingGo Technical Test

We are delighted that you are considering joining us at BookingGo. As part of our recruitment, we will be looking at your approach to problem solving and coding.  With this in mind, we ask that you complete the following exercise.

Do not over engineer your solution - keep it simple. The things we are looking for are:
* High quality code
* Your test approach
* Problem solving

Please make sure your code compiles and runs

Once complete, you can submit your code to us by sharing an open GitHub repository.

## Introduction

Our Rides platform allows customers to book professional cars and drivers across the globe. Typically, customers are travelling either to or from an airport, although journeys can be between any two points.

To fulfil bookings we work with local partners, often through APIs. At the end of this exercise you will have built a simple search and fulfilment engine that can obtain data from suppliers, aggregate this data and present it in a format which allows our customers to choose the best option for them.

For this tasks below, you will be using three supplier APIs: Dave's Taxis, Eric's Taxis and Jeff's Taxis.

| Supplier | API URL |
| - | - |
| Dave's Taxis | https://techtest.rideways.com/dave |
| Eric's Taxis | https://techtest.rideways.com/eric |
| Jeff's Taxis | https://techtest.rideways.com/jeff |

Documentation for the APIs can be found [here](api.md)

## Part 1

* Build a console application which calls the API of "Dave's Taxis". Print out the search results to the console in descending price order. Each line of the output should be in the format `{car type} - {price}`

    The console app should take pickup and drop off locations as command line parameters. Both are specified as `latitude, longitude`, for example the pickup location for London Heathrow is `51.470020,-0.454295`

* The API has limited functionality, and returns options that may not be relevant to the customer. Add logic to limit the output by taking into account the maximum number of passengers a car can hold. Add the number of passengers to your method as a parameter. 
    
    You can find the maximum number of passengers each car type can hold in the table below.

| Car Type | Maximum passengers |
| - | - |
| STANDARD | 4 |
| EXECUTIVE | 4 |
| LUXURY | 4 |
| PEOPLE_CARRIER | 6 |
| LUXURY_PEOPLE_CARRIER | 6 |
| MINIBUS | 16 |

* The Rides team have more than one supplier in most locations. Extend the functionality of the console application to call the APIs of "Eric's Taxis" and "Jeff's Taxis" as well. For each car type, choose the cheapest supplier to include in your output. There should only be one supplier chosen per car type.

    Each line of the output should be in the format `{car type} - {supplier} - {price}`

### Notes

* Not every supplier has every car type available - you may not get 6 results from every supplier.

* Supplier APIs can sometimes break, you need to be able to handle this gracefully.

* Supplier APIs can sometimes be slow. You should give a supplier 2 seconds to respond, if you do not receive a response within that time frame you should ignore the supplier for that search.

## Part 2
Using the code you created in Part 1, extend the application to provide the output through a REST API using one of the following languages:
* PHP
* JavaScript (Node, Angular are also acceptable)
* Java
* Scala

Your API should return a json payload.
