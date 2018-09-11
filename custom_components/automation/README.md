Set a cooldown for the automation (times/day/week/month), so its only trigger once per day, or every X minutes

Most cases you only use 1 option out of the following:

Config:
```
automation:
  - alias: 'automation'
    cooldown:
      # Set a cooldown for 30 seconds 'hours:minutes:seconds'
      time: '00:00:30'
      # Set a cooldown for the current day starting from 00:00:00 to 24:00:00
      once_per_day: true
      # Set a cooldown for the current week starting from monday to sunday
      once_per_week: true
      # Set a cooldown for the current month starting from the first to last day of the month (eg 01-31)
      once_per_month: true
    trigger:
    condition:
    action:
```
