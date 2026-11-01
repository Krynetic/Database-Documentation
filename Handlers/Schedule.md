# Schedule (`@Schedule`)

A schedule writes a block of content to a target path on a timetable.

## Resource layout

```text
/@Schedule/<name>
    Expression        required   When to run (cron, interval or time span)
    Target            required   Path to write to
    Content           required   The node to write (an object)
    LastTriggeredUTC  read-only  Updated at every run
```

## Example

Update `/blog` every 15 seconds:

```text
set /@Schedule/blog {
  Expression "*/15 * * * * *"
  Target "/blog"
  Content {
    title.expression "'Welcome to my blog, time is ' + now()"
  }
}
```

Subscribers to `/blog/title` receive:

```text
Welcome to my blog, time is 2026-10-27 20:00:00 +00:00
Welcome to my blog, time is 2026-10-27 20:00:15 +00:00
Welcome to my blog, time is 2026-10-27 20:00:30 +00:00
Welcome to my blog, time is 2026-10-27 20:00:45 +00:00
```

An ordinary `get` returns the latest value:

```text
get /blog/title
-> "Welcome to my blog, time is 2026-10-27 20:00:45 +00:00"
```

### The same schedule through GraphQL

Names such as `title.expression` are not valid GraphQL field names, so send the schedule as a variable:

```graphql
mutation Schedule($value: JSON) {
  set(key: "/@Schedule/blog", value: $value)
}
```

```json
{
  "value": {
    "Expression": "*/15 * * * * *",
    "Target": "/blog",
    "Content": {
      "title.expression": "'Welcome to my blog, time is ' + now()"
    }
  }
}
```

## Schedule expressions

### Cron

Standard five-field cron, or six-field cron with seconds first. Cron times are in **UTC**.

| Format | Fields |
|---|---|
| 5-field | `minute hour day-of-month month day-of-week` |
| 6-field | `second minute hour day-of-month month day-of-week` |

| Expression | Meaning |
|---|---|
| `*/15 * * * * *` | Every 15 seconds |
| `0 * * * * *` | Every minute, on the minute |
| `*/5 * * * *` | Every 5 minutes |
| `0 3 * * *` | Every day at 03:00 UTC |
| `0 9 * * 1-5` | Weekdays at 09:00 UTC |
| `0 0 1 * *` | The first day of each month at midnight UTC |

### Interval

A whole number greater than zero followed by a unit: `30s`, `5 minutes`, `2h`.

| Unit | Accepted spellings |
|---|---|
| Milliseconds | `ms`, `msec`, `msecs`, `millisecond`, `milliseconds` |
| Seconds | `s`, `sec`, `secs`, `second`, `seconds` |
| Minutes | `m`, `min`, `mins`, `minute`, `minutes` |
| Hours | `h`, `hr`, `hrs`, `hour`, `hours` |
| Days | `d`, `day`, `days` |
| Weeks | `w`, `week`, `weeks` |
| Months | `month`, `months` (calendar months) |
| Years | `y`, `yr`, `yrs`, `year`, `years` (calendar years) |

Intervals from milliseconds to weeks repeat on a constant period starting when the schedule is created. Month and year intervals follow the calendar.

### Time span

A time span such as `00:05:00` is also accepted and repeats on that period.

## Behaviour

- On every run the schedule writes `Content` to `Target` and evaluates any expressions in `Content` again, which is why `title.expression` above shows a new time each run.
- `LastTriggeredUTC` is updated at `/@Schedule/<name>/LastTriggeredUTC` before the content is written. Updating it does not restart the schedule.
- Changing `Expression`, `Target` or `Content` replaces the running job. Removing the resource stops it.
- An invalid `Expression` is reported as `Invalid schedule expression: <expression>` and the schedule does not run.
- With [persistent storage](../Getting-Started/Configuration.md#persistent-storage) schedules start again after a restart.

## More examples

Reset a value every night:

```text
set /@Schedule/nightly-reset {
  Expression "0 3 * * *"
  Target "/log"
  Content {
    today ""
  }
}
```

Count a heartbeat every 10 seconds with an [operation](../Operations.md):

```text
set /@Schedule/heartbeat {
  Expression "10s"
  Target "/status/heartbeat"
  Content { _op "increment" value 1 }
}
```

Keep a clock value fresh once a second:

```json
{
  "Expression": "1s",
  "Target": "/clock",
  "Content": { "now.expression": "now()" }
}
```
