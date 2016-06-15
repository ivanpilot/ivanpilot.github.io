---
layout: post
title:  "Introduction to the creation of a Ruby Gem"
date:   2016-06-10 10:08:18 -0400
---


https://github.com/ivanpilot/country_profile_cli_gem

Ladies, Gents,

I recently created my first Ruby Gem. It is more for a training purpose than for anything else at this stage but the seed will grow and in the near furture I will be able to share better and more useful and advanced gems for the benefit of all.

**The Gem provides a summary country profile with key indicators including population, density of population, labor force, GDP, GDP growth, etc. for almost every country in the world. It also provides for each indicator shown in the country profile, the evolution of the indicator over time up to 40 years back in time**

The data are sourced from the World Bank database, are free of access at the time I am writing this post. The gem allows you to add any indicator you wish provided it is an indicator followed by the World Bank and that you know the code name of the indicator (you can search it on the world bank website). In case you want to add an indicator, you only need to modify the output.rb file and/or the constants.rb file. You are free to do so if you wish and you could use my Gem as a starting base to create your own.

To construct this Gem, I scrapped an html page and used the World Bank free API:

1. The scrapping part consist of retrieving data programatically. It scrapes a World Bank's webpage displaying a table which links every country name or zone (eg. European Union) to a 3-letter alpha isocode (eg. 'BRA' for Brazil). This entire table of country names and their corresponding isocode is stored into a hash whose keys and values are respectively the former and the latter. This allows the user to enter a country name rather than the country isocode which might not be known directly by the user.
2. The World Bank provides an API which allows to retrieve data for a specific country using its isocode. The data could be either for a given year or for a given period of time and are available under 3 different formats. I retained the JSON format.

Once the gem installed and running, the user can choose to display the list of countries which are available, to retrieve indicators for a specific country or zone (eg. European Union) by typing the name of the desired country (please make sure you type the name as it is showed in the list of countries) or to exit the program. If the user chooses to display the profile of a country, he can then, for this same country, obtains a history of a specific indicator over a period of time up to 40 years back in time. To display the historical value of a specific indicator, the user must select the desired indicator by providing its number (range from 1 to 9 as indicated in the country profile) and indicate over how many years back in time he would want to go back. This will display the evolution of this specific indicator over the period of time he chooses. Once displayed, he can either choose to display the evolution of a new indicator over a new period of time or to exit to come back to the main menu.

All data and information are sourced from the World Bank database. All data showed for country profile are dated 2014. 2014 are the most up to date data available for now.

For more info on the Gem, you can consult the NOTES.md file or read the various files composing the gem at https://github.com/ivanpilot/country_profile_cli_gem

With the above link, you can access the README.md file for more thorough indication regarding the Gem itself and you can also get a more technical understanding of the methods and classes that have been created and used by looking at the NOTES.md file and each of the files saved under the 'lib' folder.

Although not very complicated from a technical point of view, the creation of this Gem took me some time, tests and trials until it worked well. I hope you will enjoy it and if you have any comments and / or wish to share anything, please feel free to contact me. My contact details are in the README.md file.

Sincerely,
