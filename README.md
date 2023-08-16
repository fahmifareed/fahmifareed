# Visit https://github.com/lowlighter/metrics#-documentation for full reference
name: Metrics
on:
  # Schedule updates (each hour)
  schedule: [{cron: "0 * * * *"}]
  # Lines below let you run workflow manually and on each commit
  workflow_dispatch:
  push: {branches: ["master", "main"]}
jobs:
  github-metrics:
    runs-on: ubuntu-latest
    permissions:
      contents: write
    steps:
      - uses: lowlighter/metrics@latest
        with:
          # Your GitHub token
          # The following scopes are required:
          #  - public_access (default scope)
          #  - read:user
          #  - read:org
          #  - public_repo
          #  - read:project
          # The following additional scopes may be required:
          #  - read:org      (for organization related metrics)
          #  - read:user     (for user related data)
          #  - read:packages (for some packages related data)
          #  - repo          (optional, if you want to include private repositories)
          token: ${{ secrets.METRICS_TOKEN }}

          # Options
          template: classic
          base: header, activity, community, repositories, metadata
          config_timezone: Africa/Cairo
          plugin_16personalities: yes
          plugin_16personalities_scores: yes
          plugin_16personalities_sections: personality
          plugin_fortune: yes
          plugin_habits: yes
          plugin_habits_charts_type: classic
          plugin_habits_days: 14
          plugin_habits_facts: yes
          plugin_habits_from: 200
          plugin_habits_languages_limit: 8
          plugin_habits_languages_threshold: 0%
          plugin_introduction: yes
          plugin_introduction_title: yes
          plugin_languages: yes
          plugin_languages_aliases: Python
          plugin_languages_analysis_timeout: 15
          plugin_languages_analysis_timeout_repositories: 7.5
          plugin_languages_categories: markup, programming
          plugin_languages_colors: github
          plugin_languages_indepth: yes
          plugin_languages_limit: 10
          plugin_languages_other: yes
          plugin_languages_recent_categories: markup, programming
          plugin_languages_recent_days: 14
          plugin_languages_recent_load: 300
          plugin_languages_sections: most-used
          plugin_languages_threshold: 0%
          plugin_leetcode: yes
          plugin_leetcode_limit_recent: 2
          plugin_leetcode_limit_skills: 10
          plugin_leetcode_sections: solved
          plugin_leetcode_user: .user.login
          plugin_lines: yes
          plugin_lines_history_limit: 1
          plugin_lines_repositories_limit: 4
          plugin_lines_sections: base
          plugin_nightscout: yes
          plugin_nightscout_datapoints: 12
          plugin_nightscout_highalert: 180
          plugin_nightscout_lowalert: 80
          plugin_nightscout_urgenthighalert: 250
          plugin_nightscout_urgentlowalert: 50
          plugin_nightscout_url: https://example.herokuapp.com
          plugin_pagespeed: yes
          plugin_pagespeed_url: .user.website
          plugin_people: yes
          plugin_people_limit: 24
          plugin_people_size: 28
          plugin_people_types: followers, following
          plugin_posts: yes
          plugin_posts_limit: 4
          plugin_posts_user: .user.login
          plugin_projects: yes
          plugin_projects_limit: 4
          plugin_repositories: yes
          plugin_repositories_order: featured, pinned, starred, random
          plugin_screenshot: yes
          plugin_screenshot_background: yes
          plugin_screenshot_mode: image
          plugin_screenshot_selector: body
          plugin_screenshot_title: Screenshot
          plugin_screenshot_viewport: {
  "width": 1280,
  "height": 1280
}

          plugin_sponsors: yes
          plugin_sponsors_sections: goal, list, about
          plugin_sponsors_size: 24
          plugin_sponsors_title: Sponsor Me!
          plugin_stackoverflow: yes
          plugin_stackoverflow_limit: 2
          plugin_stackoverflow_lines: 4
          plugin_stackoverflow_lines_snippet: 2
          plugin_stackoverflow_sections: answers-top, questions-recent
          plugin_stargazers: yes
          plugin_stargazers_charts: yes
          plugin_stargazers_charts_type: classic
          plugin_stargazers_days: 14
          plugin_starlists: yes
          plugin_starlists_limit: 2
          plugin_starlists_limit_languages: 8
          plugin_starlists_limit_repositories: 2
          plugin_starlists_shuffle_repositories: yes
          plugin_stars: yes
          plugin_stars_limit: 4
          plugin_topics: yes
          plugin_topics_limit: 15
          plugin_topics_mode: starred
          plugin_topics_sort: stars
          plugin_tweets: yes
          plugin_tweets_limit: 2
          plugin_tweets_user: .user.twitter
