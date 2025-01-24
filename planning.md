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