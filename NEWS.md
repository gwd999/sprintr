# sprintr 0.1.2.900

## New Features

* `get_sprint()` now returns a tibble instead of a data.frame, consistent 
with other functions
* `get_issue()` returns also returns the issue summary, description, and resolution
* `get_issue()` and `get_issues_by_epic()` both check if the story point 
mapping has been refreshed in the current session and will auto refresh if 
necessary. This behavior can be disabled by setting the option 
"sprintr_storypoint_mapping" to TRUE.

## Bug Fixes

* Switch from using `anytime::anydate()` to `lubridate::as_date()` to avoid UTC 
parsing problems with ISO8601 datetimes in issue responses.

# sprintr 0.1.2

## New Features

* `get_epic()` retrieves summary information on a specific epic ID.
* `get_epics()` retrieves summary information for all epics under a certain board ID.
* `get_issues_by_epic()` retrieves all issues for a specific epic.
* `get_issues_on_backlog()` can take an optional JQL string through which results are filtered.

# sprintr 0.1.1

* NEW FEATURE - Initial Oauth1.0 support - clunky, but functional.
* Use package globals to configure commonly used custom fields
* `find_story_point_mapping()` detects the customfield id for story point fields
* Use the V2 API whenever possible over the V3 calls. V3 of the Jira API is not 
  available for on prem deployments and is still beta even for cloud environments.
* Bug fix - `jira_api_post()` calls were broken. :(
* Bug fix - `get_board_details()` was calling the sprint details endpoint accidentally.
* Remove support for the JSESSION_ID hack and document that JIRA_USER and 
  JIRA_TOKEN can be (mis)used to perform basic authentication.


# sprintr 0.1.0

* Internal functions for working with `sprintr` environment variables can now 
  set as well set get their values. This is intended for development purposes.
* Bare bones support for Jira Server API calls via the JSESSION_ID hack.

# sprintr 0.0.0.9000

* `get_sprint_report_detail()` takes a board_id and a sprint_id parameter.
* `get_sprints()` renamed to `get_all_sprints()`.
* `get_sprint()` introduced to fetch details of a particular sprint.
* `get_boards()` now properly follows pagination (@quartin).
* `JIRA_API_KEY` properly documented (@quartin).
* `epic_name` correctly parsed from issues.
* Basic documentation added to functions.
* Added a `NEWS.md` file to track changes to the package.
