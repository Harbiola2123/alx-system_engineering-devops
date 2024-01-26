			ISSUE SUMMARY & TIMELINE
On Thursday 26th January 2023 at 9 am , some of our customers may have noticed an issue that created intermittent 500 error pages while viewing apps and crash reports
			Root cause
The root of the error was an IIS application pool in a bad state. This was affecting a third party library that is used to connect to one of our backend databases (redis). As a result, any request to the database would return the data but the third party library would throw a low-level error trying to read the returned data stream

		 	
resolution 	
The issue was resolved when the application pool was recycled. The byproduct of this is the bad state was cleared, and the new application pool started functioning correctly. All requests to the application after this time completed successfully
Corrective and preventive measures
 We Made we maintain log files, empty the recycling bin, delete files in temporary folders, and defragment hard drives tasks to preserve performance levels and avoid system overload.  And also Develop a server contingency plan

