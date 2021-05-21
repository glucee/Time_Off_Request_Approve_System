# Time_Off_Request_Approve_System
Request and approve time off Apps Script Enhancement for Google Form and Google Calender, based on the public [article](https://docs.google.com/document/d/1y6x90S_q_cwdl4LGVDDSqMyuikx1zmPFyVQfSlYsKLk/). I made some changes in both form and code to make it work.

This solution allows end users to submit vacation requests to be approved or denied by approving members. The approving members will receive an email that contains an Approve / Deny link. When the approver clicks Approve or Deny, the response is updated in the corresponding spreadsheet and an email is generated and sent to the requestor. If the request has been approved, the calendar event is automatically added both to a vacation calendar and to the requestor’s calendar.

## Solution Components

The following components make up the solution:
* Google Calendar - a vacation calendar
* Google Form - a form that the end user of the system can use to request vacation time or other time off
* Google Sheet - a spreadsheet that contains the responses to the submitted form and the Apps Script to process the requests
* Apps Script - a script within the spreadsheet, that is triggered each time the form is submitted
For additional reference, following the configuration instructions, you’ll find a copy of the Apps Script code and screenshots highlighting key points of the procedure.

## Configuration Instructions

1. Open this [spreadsheet](https://docs.google.com/spreadsheets/d/1km6wVNkPFDbwxJUbatLAx9K6os8bUbAG2c7WgGndpOk) and make a copy (File > Make a copy).  
In your Drive, you’ll also see a copy of the form, which you are then free to edit.  
2. In Google Calendar, create a vacation calendar. Make sure that the owner of the calendar is also the owner of the script.  
3. In the newly created vacation calendar, capture the Calendar ID (under Calendar Address in the calendar’s settings).  
4. In the "__Settings" sheet of your copy of the spreadsheet, replace the existing Calendar ID with the Calendar ID of the vacation calendar you just created.  
5. In your copy of the spreadsheet, capture the Spreadsheet Key.    
This is the part of the URL between the two slashes following the “d,” highlighted here: https://docs.google.com/spreadsheets/d/…./  
6. From the spreadsheet menu, open the Script Editor (Tools > Script editor).  
** I have made some change to the code to make it work with the form 
8. In the Script Editor, replace the SPREADSHEET_KEY variable value (inside the quotes) with the Spreadsheet Key for this spreadsheet, captured in step 5.  
9. Save the code changes.  
10. Run any function in the Run menu and authorize the script for use. You will be asked to review and authorize account permissions. Ignore the trigger error message in red.  
11. In the Script Editor menu, click Resources > Current project’s triggers to set up a new trigger.  
a. In the dialog, for the first field, select OnFormSubmit. For the second, select From spreadsheet. For the third, select On Form Submit.  
b. Optionally, click notifications and set up an email address that will receive failure notifications.   
c. Save.  
12. In the Script Editor menu, click Publish > Deploy as web app.   
a. In the dialog, enter a description for the new version, select Execute as Me, select Anyone within <domain>, and click Deploy.   
b. In the subsequent dialog, click OK.   
13. Click the 'Deploy' button in the right corner, and then select 'Test Developments', under URL of Web APP, click 'copy'  
8. In the Script Editor, replace the SCRIPT_URL variable value with the URL value, captured in last step.  
9. Save the code changes. 
15. Exit the Script Editor.  
16. In the spreadsheet menu, click the Form > Edit form.  
a. In edit mode for the form, edit the answers for manager’s email, including the email addresses of the managers in your department who will approve leave requests.  
Make sure the spreadsheet columns are appropriately named.   
b. If you make a change to the text in the form questions, this will change the column names, which will also affect the code in several places that rely on specific column names.   
c. For the values to be properly replaced for the emails that get generated, the column names must match the values in the {{}} brackets in the __Settings tab templates.      
d. The order of the columns does not matter.  
17. Run a test by filling out the time-off form and submitting a response.  

## Credit
https://docs.google.com/document/d/1y6x90S_q_cwdl4LGVDDSqMyuikx1zmPFyVQfSlYsKLk/
