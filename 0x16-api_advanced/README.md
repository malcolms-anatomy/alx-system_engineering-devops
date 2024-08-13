# Reddit API Project

This project includes Python scripts that interact with the Reddit API to perform various tasks. The scripts use recursion to handle API pagination and query hot posts from subreddits.

## Table of Contents

1. [Task 0: Number of Subscribers](#task-0-number-of-subscribers)
2. [Task 1: Top Ten](#task-1-top-ten)
3. [Task 2: Recurse It!](#task-2-recurse-it)
4. [Task 3: Count It!](#task-3-count-it)
5. [Usage](#usage)
6. [Requirements](#requirements)

## Task 0: Number of Subscribers

**File:** `0-subs.py`

**Function:** `number_of_subscribers(subreddit)`

**Description:** Queries the Reddit API to return the number of subscribers for a given subreddit. If the subreddit is invalid, returns 0.

**Usage Example:**
```bash
$ python3 0-main.py programming
756024

$ python3 0-main.py invalid_subreddit
0
```

## Task 1: Top Ten

**File:** `1-top_ten.py`

**Function:** `top_ten(subreddit)`

**Description:** Queries the Reddit API and prints the titles of the first 10 hot posts listed for a given subreddit. If the subreddit is invalid, prints `None`.

**Usage Example:**
```bash
$ python3 1-main.py programming
Firebase founder's response to last week's "Firebase Costs increased by 7000%!"
...
Google Bug Bounty - The 5k Error Page

$ python3 1-main.py invalid_subreddit
None
```

## Task 2: Recurse It!

**File:** `2-recurse.py`

**Function:** `recurse(subreddit, hot_list=[])`

**Description:** Recursively queries the Reddit API and returns a list containing the titles of all hot articles for a given subreddit. If no results are found, returns `None`.

**Usage Example:**
```bash
$ python3 2-main.py programming
932

$ python3 2-main.py invalid_subreddit
None
```

## Task 3: Count It!

**File:** `100-count.py`

**Function:** `count_words(subreddit, word_list)`

**Description:** Recursively queries the Reddit API and parses the title of all hot articles to count the occurrences of keywords from `word_list`. Results are printed in descending order by count, with ties sorted alphabetically. Words with no matches are skipped.

**Usage Example:**
```bash
$ python3 100-main.py programming 'react python java javascript scala no_results_for_this_one'
java: 27
javascript: 20
python: 17
react: 17
scala: 4

$ python3 100-main.py programming 'JavA java'
java: 54
```

## Usage

To run the scripts, you need to have Python 3.x installed. Use the following commands to execute each script:

```bash
$ python3 0-main.py <subreddit>
$ python3 1-main.py <subreddit>
$ python3 2-main.py <subreddit>
$ python3 100-main.py <subreddit> '<keyword1> <keyword2> ...'
```

Replace `<subreddit>` with the name of the subreddit you want to query and `<keyword1> <keyword2> ...` with the keywords you want to count.

## Requirements

- Python 3.x
- Requests library (install via `pip install requests`)
- The scripts should be executable (`chmod +x <script.py>`)

All scripts are designed to be run on Ubuntu 20.04 LTS and use Python 3.4.3.

---
