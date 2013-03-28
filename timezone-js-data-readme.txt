1   Get latest timezone data
1.1   Goto http://www.iana.org/time-zones
1.2   Download latest Time Zone Data, e.g. http://www.iana.org/time-zones/repository/releases/tzdata2013b.tar.gz
1.3   Extract to a new directory called "tzdataXXX", e.g. "tzdata2013b"

2   Bundle timezone data
2.1 Open cygwin in main timezone-js directory
2.2 run: node src/node-preparse.js tzdataXXX/ > tzdataXXX.json
2.3 Open tzdataXXX.json in a text editor
2.4 Prepend: timezoneJS.timezone.loadZoneDataFromObject(
2.5 Append: );
2.6 Prepend new line: timezoneJS.timezone.loadingScheme = timezoneJS.timezone.loadingSchemes.MANUAL_LOAD;
2.7 Save as tzdataXXX-t.js

3 Closure
3.1 run: java -jar ./utils/closure/compiler.jar --js ./tzdataXXX-t.js --js_output_file ./tzdataXXX.js