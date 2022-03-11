# LoL-Gambling
Made by Tyler Safe in 2022

Description:

Over/under kill total model that utilizes a UI, scrapes all required statistics, performs calculations and has data on upcoming games. This is accomplished using PyQt5 for the UI and a bunch of Python libraries listed below in Installation. This program was designed for research/educational purposes and allows for easy access to specific stats that are otherwise difficult to come by. The updating of stats can sometimes take up to 20s as for a single league over 20 different webpages may need to be accessed. The maintenance of the code is also quite high in that all urls need to be updated every split (every 6 months) for the code to continue to work properly, see the maintenance section below. I hope to add some additional features including a date for each game, which has proved to be more difficult than expected.

Installation:

- To run the program you will require Python 3 or later as well as the following libraries: requests, BeautifulSoup, PyQt5, sys and openpyxl
- Download the contents of the repository as a zip and extract it to your desired location
- Run the Python code

How to Use:

- The first page contains a table with upcoming games for the current day and the next, this can be used to determine which leagues to look at for the day
- Each button when clicked will take you to that leagues page where the statistics, ladder and upcoming games are displayed
- The ladder is always up to date and scraped upon accessing the page, it can be used to determine whether the statistics table is out of date (record/matches different)
- The statistics table consists of team name, number of matches played, teams average kills over current season, the % chance of the team going over past games kill line and then repeated for game 2/all games. This is loaded from the relevant excel doc upon accessing the page to save time, the refresh retrieves new data.
- The statistics table can be updated using the Update button below it, this will scrape all fresh information from the relevant sites and can take up to 20s
- The upcoming games table consists of all games that have lines currently listed for the given league, along with the calculation to determine if their is any value in the line
- Due to gambling sites having anti-scraping measures a default value is used (different for each league) along with default odds of 1.83 (standard) for the calculation
- If the odds/line are different to the default displayed you can change them by entering new values in the 'Line:' and 'Odds:' text boxes, pressing Calculate then redoes the calculation using the new input
- Value is determined using a model with weightings and reflects the expected ROI

Maintenance:

- After each split the links to each scoreboard page and league homepages will need to be updated
- If a leagues average kills changes that will need to be updated in the get_league and league_data function calls
- If new teams join leagues or teams change their name it will need to be updated in the league_data calls and possibly the load_data function
