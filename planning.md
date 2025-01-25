# Plan

JSON compatible specification with part types and variants. A part class requires a generic set of
tags, and types within that class must provide those tags plus any additional that are relevant
to the part itself. The OOPS project shall provide the syntax for describing specific parts, and a 
list of classes and variants with their required tags. Long-term, OOPS shall also supply parsers
written in a variety of languages for easy inclusion into other projects.

OOPS is being developed as a part of an on-going project to build a unified parts storage and 
management system (yet to be published). Its goal is to be a standard description for electronic
parts. Thus, it shall describe the important parameters of any given part, and leave room for an
application to add its own application specific parameters.


Conceptual syntax

```json
{
    // Version number for the oops format
    "v" : "0.0.3",
    // Part number / manufacturing number
    "part_number" : "STM32G4",
    // this are the sub types of the capacitor
    // this is added as Tantalum Capacitors 
    // will have addtional information when 
    // compared to something like an electrolytic
    // capacitor
    // these tags can also be used for searching.
    "type" : "Micro-Controller",
    "package" : "QFN64",
    "tags" : [
        "3v3",
        "i2c",
        "usart",
        "spi",
        "ADC",
        "DACs",
        "GPIOs",
    ],
    "parameters" : {
        "Micro-Controller" : {
            "ram" : 64000,
            "speed" : 64e6,     
        },
        "DACs" : [
            {
                "pin" : 3,
                "Vmax" : 3.3,
                "max_freq" : 2000,
            },
            {
                "pin" : 4,
                "Vmax" : 3.3,
                "max_freq" : 5000,
            },
        ],
        "QFN64" : {},
    },
    "datasheets" : [
        "https://https://www.digikey.co.nz/",
    ],
    "suppliers" : [
        "https://https://www.digikey.co.nz/",
    ],
    // user defined data, this is useful if you want your
    // applaction to use things like custom images for your
    // parts, or have notes for each of them,
    // it is suggest each app uses its own name space for 
    // custom data to avoid clashes 
    "custom_data" : {

        // just as an example of what could be added here
        "CanSource.PartsFinder" : {
            "quantity" : 10000,
            "location" : "Shelf B15",
            "notes" : "these are kinda slow",
            "search_tags" : [
                "SMD",
                "0603",
            ]
        }
    },
}
```