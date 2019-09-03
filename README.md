Hopper Quant Analyst Exercise
===

Background
---

Hopper receives several billion priced air itineraries every day, in near real-time.
Each trip is part of a bundle of trips indicated by a search identifier.
Usually a bundle of trips is a set of alternative flights resulting from
a consumer flight search at an online travel agency (OTA).
For example, a user might search for flights from BOS to JFK, perhaps including nearby airports,
with particular (possibly flexible) departure and return dates.
The search returns many possible priced trip options, which forms a bundle of trips.
Hopper doesn't receive any information about whether a trip was purchased,
what the original query was, or any user-identifiable information.

Files
--

 - README.md: this file
 - boscun-longitudinal.csv.gz, a gzipped CSV file with about 3M trip records collected for a particular route
 - metadata for the CSV is provided below
 
Goal
---

This exercise includes a small sample of all the searches we saw for round-trip flights from Boston to Cancun
over a period of about 18 months, with a small subset of potentially interesting features for each trip.
Imagine that a Hopper user wants to travel this route on particular departure and return dates, 
and checks the price on some earlier date.  
Illustrate how you'd use a dataset like this to advise the user at that time whether they should buy the ticket
or wait for a better price.

We're not expecting a production-quality solution, and are more interested in your approach and understanding of the issues involved.  Please feel free to use whatever tools you like, 
and provide a short discussion (max 500 words) outlining your findings, methodology,
and any key remaining issues you'd want to tackle in production.

Metadata
---

- search_id: the bundle identifer 
- trip_index: the index of the trip within a bundle
- received_date: date the trip was received at Hopper
- received_ms: epoch milliseconds trip was received
- origin: origin airport
- destination: destination airport
- total_usd: total fare including taxes and fees
- pax_type: passenger type quoted
- refundable: refundable fare indicator
- validating_carrier: airline selling the ticket
- departure_odate: departure date in origin TZ
- departure_ms: epoch milliseconds of departure
- outgoing_duration: total in minutes 
- outgoing_stops: number of stops on outbound trip
- return_odate: return date in destination TZ
- return_ms: epoch millis of return time
- returning_duration: total in minutes
- returning_stops: number of stops on return trip
- major_carrier_id: airline delivering majority of flight time
- total_stops: total stops for round-trip
- advance: days search before departure
- length_of_stay: nights between departure and return
- includes_saturday_night_stay: indicator for saturday stayover
- available_seats: quoted availability at search time
- lowest_cabin_class: lowest cabin class over all flights
- highest_cabin_class: highest cabin class over all flights

