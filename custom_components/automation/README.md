Set a cooldown for the automation (times/day/week/month), so its only trigger once per day, or every X minutes.

Its required to use the recorder, because the attribute last_triggered needs to be safed and restored. Otherwise the cooldown is not restored after HA restart and cooldown reset

In most cases you only use 1 option out of the following:

Config:
```
automation:
  - alias: 'AUTOMATION_ID'
    cooldown:
      # Set a cooldown for 30 seconds 'hours:minutes:seconds' (default None)
      time: '00:00:30'
      # Set a cooldown for the current day starting from 00:00:00 to 24:00:00 (default False)
      once_per_day: true
      # Set a cooldown for the current week starting from monday to sunday (default False)
      once_per_week: true
      # Set a cooldown for the current month starting from the first to last day of the month (eg 01-31) (default False)
      once_per_month: true
    trigger:
    condition:
    action:
```

If you want to reset the automation and delete the current cooldown, you can use the service: automation.cooldown_reset
```
# resets the cooldown for the automation. So it can be triggered again
- service: automation.cooldown_reset
  entity_id: automation.AUTOMATION_ID
```
