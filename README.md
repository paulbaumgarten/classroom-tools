# Classroom tools

## School timer

A count down to the next timetable transition for STC.

* Live link: [https://paulbaumgarten.github.io/classroom-tools/school-timer.html](https://paulbaumgarten.github.io/classroom-tools/school-timer.html)

## Seating plan

A tool for visualising seating plans

* Live link: [https://paulbaumgarten.github.io/classroom-tools/seating-plan.html](https://paulbaumgarten.github.io/classroom-tools/seating-plan.html)

Export your classlist from SMART, or create your own CSV with these fields: `Surname`, `Firstname`, `Tutor Group`, `IdNo`

Export the photos ZIP file for your classlist from SMART, or create your own whereby photo filenames end with the `IdNo` and photos are in JPG format.

All processing happens in your local browser. No student information is transmitted to the server.

## Random student picker

Randomly selects a student from a classlist with a 3-second animated draw, then lets you return the student to the pool or remove them.

Classlists are saved in browser storage, and can be imported/exported as JSON for backup and transfer.

* Live link: [https://paulbaumgarten.github.io/classroom-tools/random-student-picker.html](https://paulbaumgarten.github.io/classroom-tools/random-student-picker.html)

## Class groups maker

Create evenly balanced random student groups by choosing the number of groups to form.

Uses the same browser classlist storage and JSON import/export format as the random student picker.

Supports hidden "lock pairs apart" constraints via data (not shown in the UI), so specific students are kept in different groups where possible.

To use lock pairs:

1. Export your classlists JSON from either tool.
2. Add an optional `lockPairs` array to a classlist entry using exact student names, e.g.

```json
{
  "className": "Year 9 Science - Period 2",
  "names": ["Alex Tan", "Riley Jones", "Jordan Singh"],
  "lockPairs": [["Alex Tan", "Riley Jones"], ["Jordan Singh", "Alex Tan"]]
}
```

3. Re-import JSON. The groups maker will apply these constraints silently during grouping.

Notes:
- `lockPairs` are optional and ignored if names do not match current classlist names.
- Constraints are preserved when saving/editing classlists in either tool.
- If all constraints cannot be fully satisfied, the groups maker still produces the most balanced result it can and reports remaining conflicts.

* Live link: [https://paulbaumgarten.github.io/classroom-tools/class-groups-maker.html](https://paulbaumgarten.github.io/classroom-tools/class-groups-maker.html)
