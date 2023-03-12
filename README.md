# Smite-God-Build---Project
Webapplication that analyzes "build" data from SMITE and consolidates it into suggested builds for players for each god.

Smite is a M.O.B.A that has many playable characters that each require building items throughout the course of a match. These items may vary per god (playable character) therefore it can be hard for a player to choose a build that is effective especially with the shifting "META" of builds as patches adjust items' efficacy.

Goals:
-Produce a suggested build for all available gods based on community usage.
-Chosen items will be based on win rate and no. of matches per item.
-Builds will update as data shifts.

Details:
All data on item usage, playable gods, item names, images will be acquired from the Smite API.

Project flow is as follows; Create initial database and populate with playable gods and list of items that can be built on each god using the API. Collect usage data using a series of API calls (Limited to 7500 calls per day, will get as much data as possible per day)
-getmatchidsbyqueue to get a list of match ids from the Ranked Conquest Queue
-getmatchdetailsbatch to get information of all ids acquired by previous step.
Scan through data to make note of gods and what items were built and whether it was a win.
Process data and save under god listings in database, gods have all items they can build list with a counter for wins and total matches played as well as item info like name and link to image. Each god will have slots 1-6 which have its suggested items which are updated as data changes.

Javascript will call the suggested build from an endpoint and update front end display with images for suggested items acquired through Smite API. Suggested build will be determined by a comparison of win rate and no. of matches. Win rate decides on the item based on items with at least X no. of matches. X will be determined by data analysis.

Notes:
Database will be handled by MongoDB with a local instance. Node js will be used for data processing and setting up the endpoint for javascript and front-end to access. 

Full support for the project would lead to a hosted database on AWS or another host.


HOW TO RUN:
