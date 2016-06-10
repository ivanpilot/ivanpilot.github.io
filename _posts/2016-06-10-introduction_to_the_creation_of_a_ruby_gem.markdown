---
layout: post
title:  "Introduction to the creation of a Ruby Gem"
date:   2016-06-10 10:08:18 -0400
---


https://github.com/ivanpilot/country_profile_cli_gem

Ladies, Gents,

I recently created my first Ruby gem. It is more for a training purpose than for anything else at this stage but the seed will grow and in the near furture I will be able to share better and more useful and advanced gems for the benefit of all.

**The Gem provides a short profile with key indicators including population, density of population, labor force, GDP, GDP growth, etc. for almost every country in the world.**

The data are sourced from the World Bank database, are free of access at the time I am writing this post, and provide information for 2014 only but it could be extended to more recent data if available and also to time series (to the extent it is available and relevant for some indicators) if you wish so, although this later option will require to implement an entire new functionality to access time series. You are free to do so if you wish and you could use my Gem as a starting base to create your own.

To construct this Gem, I scrapped an html page and used the World Bank free API:

1. The scrapping part consist of retrieving data programatically. It scrapes a World Bank's website page displaying a table which links every country name or zone (eg. European Union) to a 3-letter alpha isocode (eg. 'BRA' for Brazil). This entire table of country names and their corresponding isocode is stored into a hash whose keys and values are respectively the former and the latter. This allows the user to enter a country name rather than the country isocode which might not be known directly by the user.
2. The World Bank provides an API which allows to retrieve data for a specific country using its isocode. The data could be either for a given year or for a given period of time and are available under 3 different formats. I retained the JSON format.

When using the Gem, the user has the option to type a specific country name, the word 'list' to obtain a comprehensive list of all the countries available in the World Bank database or the word 'exit' to exit the program.

The detailed working process of the Gem consists of the following steps:

1. The user provides a country name
2. A method verifies if the country belongs to the list of available countries and returns the related country's isocode if this is true
3. A method composes 2 different url types based on the country's isocode and desired indicators and automatically retrieves the data for 2014 under a JSON format
4. The object retrieved is parsed and analysed to identify the right value for the indicator required. This is repeated as many times as the number of indicators.
5. Indicators and their related value are stored into a hash
6. For each key of the hash, the value is appropriately converted to the right unit format
7. A method creates an output to be printed on the screen that shows for each indicator its value if available under the right format

Should you wish to have more information on this Gem, visit the link below:
https://github.com/ivanpilot/country_profile_cli_gem

With the above link, you can access the README.md file for more thorough indication regarding the Gem itself and you can also get a more technical understanding of the methods and classes that have created and used by looking at each of the files saved under the 'lib' folder.

Although not very complicated from a technical point of view, the creation of this gem took me some time, tests and trials until it worked well. I hope you will enjoy it and if you have any comments and / or wish to share anything, please feel free to contact me. My contact details are in the README.md file.

Sincerely,
