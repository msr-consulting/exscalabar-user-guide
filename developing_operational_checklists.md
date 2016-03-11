# Developing Operational Checklists
Checklists may be accessed for operation via the user interface.  These checklists are recorded in the JSON file format.  
The format is written as an array of objects.  Each object represents a section in the checklist. A checklist file will look like the following:

```json
{
  "main": [
    {
      "title": "Consumable",
      "items": [
        "Check and record zero pressure.",
        "Turn on O2 cylinder.  Record O2 pressure.",
        "Replace scrubber as necessary (every 2 to 3 flights).",
        "Replace CLAP filter, if needed.  White side up.",
        "Clean impactor (20 to 30 flight hours)",
        "Check 2 water reservoir levels (clear reservoirs at rear of instrument)."
      ],
      "records": [
        {
          "name": "Pressure",
          "type": "numeric"
        },
        {
          "name": "Pressure",
          "type": "numeric"
        },
        {
          "name": "Replaced?",
          "type": "boolean"
        },
        {
          "name": "Replaced?",
          "type": "boolean"
        },
        {
          "name": "Cleaned?",
          "type": "boolean"
        },
        null
      ]
    },
    {
      "title": "Power Up",
      "items": [
        "Check that the 5 PAS Laser breakers are off.",
        "Check that bus 1 is selected for 60 Hz.",
        "Start instrument by turning on the AC master breaker. Wait for valves to cycle on before continuing. ",
        "Start host on laptop. "
      ]
    }
  ]
}
```

Each object in the array contains an entry called ``title``.  This represents the section heading.  The checklist for each section is defined by an array of strings that is called out by the entry ``items``.  On the user interface, this will be rendered as a list with each item preceded by a checkbox.
