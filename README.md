# BookingGo Techincal Test

We are delighted that you are considering joining us at BookingGo, as part of our recruitment we will be looking at your approach to problem solving and coding.  With this in mind please could you complete the following exercise.

Please do not over engineer the solution so keep it simple, the things we are looking for are:
* High quality code
* Your test approach
* Problem solving

Please submit your code to us through sharing an open GitHub repository.  

Please do make sure your code compiles and works.

## Introduction

Our Rides team allow customer to book professional cars and driver across the globe. Typically customers are travelling either to or from an airport, but journeys can be between any two points.

To fulfil bookings we work with local partners often through APIs. At the end of this exercise you will built a simple search and fulfilment engine that uses data from suppliers, agregates the data and present it in a form to allow customers to choose the best option for them.

## Part 1

* Build a console app that calls the API of "Dave's Taxis". Print out the search results to the console in descending price order. Each line of the output should be in the format `{car type} - {price}`

    The console app should take pickup and drop off as command line parameters. Both are specified as lat,longs e.g. the pickup location for London Heathrow is `51.470020,-0.454295`

* The API has limited functionality and returns options that may not be relevant to the customer. Add functionality to limit output to take into account the maximum number of passenger a car can hold. Add the number of passengers as a parameter, the maximum number of passengers each car type can hold are in the table below.

| Car Type | Maximum passengers |
| - | - |
| STANDARD | 4 |
| EXECUTIVE | 4 |
| LUXURY | 4 |
| PEOPLE_CARRIER | 6 |
| LUXURY_PEOPLE_CARRIER | 6 |
| MINIBUS | 16 |

* The Rides team have more than one supplier in most locations. Extend the functionality of the console app to call the APIs of "Eric's Taxis" and "Jeff's Taxis" as well. For each car type choose the cheapest supplier to output.

### Notes

* Not every supplier has every car type available to them - you may not get 6 results from a supplier.

* Supplier API sometimes break, you need to be able to handle this gracefully.

* Supplier APIs can sometimes be slow. You should give a supplier 2 seconds to respond, if you do not receive a respond within that time you should ignore that supplier.

| Supplier | API URL |
| - | - |
| Dave's Taxis | https://techtest.rideways.com/dave |
| Eric's Taxis | https://techtest.rideways.com/eric |
| Jeff's Taxis | https://techtest.rideways.com/jeff |

Documentation for the APIs can be found at https://technicaltest.docs.apiary.io/#reference

## Part 2
Using the code created in Part 1 extend the code to provide the output through a REST API using one of the following languages:
* PHP
* JavaScript (Node, Angular are also acceptable)
* Java
* Scala

The API should return a json payload.