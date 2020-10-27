# signal-search-api
An API to search the FCC LMS and CDBS databases for DTV signal strengths at a given location. 

This API would accept GET requests only and would require a valid API key to authorize all requests.

Input:
- required: a coordinate set within the US or Canada
- optional: search radius (default 75 miles)
- optional: minimum field strength threshold (default: 60 dbuV/m) 
- optional: accept a freq start (default 54MHz)
- optional: accept an RF Channel End ( default 614MHz, max 3GHz)
- optional: format (default JSON, but can be XML or HTML)
- optional: receive antenna height (default 15ft)

Output (formatted accordingly to input parameter, returns in less than 5 seconds):
- JSON array of Transmitter objects that match the input criteria.

The transmitter Object would contain the following properties:
- Distance and direction to transmitter from the given location
- Call Sign(or Call Signs if sharing) and Network operating on that transmitter
- RF Channel
- City/State of License
- Field Strength
- Signal Type (LMR/T-Band, DTV, Radio Astronomy, etc.)
