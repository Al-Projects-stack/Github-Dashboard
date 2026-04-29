GITHUB STATS DASHBOARD
======================
By Al Takura Mujati


DAD JOKE
--------
Why do programmers prefer dark mode?
Because light attracts bugs.


WHAT IT IS
----------
A tool that pulls any GitHub user's public profile data and displays
it in a clean dashboard. You type in a GitHub username, hit search,
and it shows their repos, followers, stars, forks, top languages,
and best repositories.


HOW IT WORKS
------------
There is no backend. This is a pure frontend project.

When you type a username and search, the browser sends a request
directly to the GitHub public API:

    https://api.github.com/users/{username}
    https://api.github.com/users/{username}/repos

These are public endpoints. GitHub allows anyone to read public
profile data without logging in or having an API key. The browser
fetches the data, JavaScript processes it, and the page updates.

This pattern is called a client-side API call. Your browser is
the client, GitHub's servers are the API, and there is no server
of your own in the middle.


THE DATA FLOW STEP BY STEP
---------------------------
1. You type a username and press Search
2. The browser sends two fetch() requests to GitHub's API
3. GitHub responds with JSON data (user profile and repo list)
4. JavaScript reads the JSON and extracts the numbers you see:
   total stars (summed across all repos), total forks, follower count
5. It loops through the repos and counts how many use each language
6. It sorts repos by star count and displays the top five
7. The language bars are drawn using plain CSS widths, calculated
   as a percentage of the most-used language


WHY NO BACKEND IS NEEDED
-------------------------
GitHub's API is publicly accessible for read-only data.
No authentication is required for public profiles.
All the logic (sorting, summing, calculating percentages) runs
in JavaScript inside the browser.

If this tool needed to store data, require login, or access
private repos, that is when a backend would be necessary.


TECH USED
---------
HTML, CSS, JavaScript
GitHub REST API v3 (public endpoints)
fetch() for HTTP requests
No libraries, no frameworks, no backend


HOW TO RUN IT
-------------
Open the HTML file in any browser with internet access.
Type any GitHub username and search.
Works with any public GitHub account.


RATE LIMITING
-------------
GitHub allows up to 60 unauthenticated API requests per hour
from the same IP address. For a portfolio project this is more
than enough. If you add a personal access token as an
Authorization header you get 5000 requests per hour.


WHY IT IS ON MY PORTFOLIO
--------------------------
It shows understanding of REST APIs, JSON data handling, and
how to work with third-party services without a backend.
It also displays real, live data about my own GitHub activity,
which makes it personal and relevant to any developer looking
at my work.
