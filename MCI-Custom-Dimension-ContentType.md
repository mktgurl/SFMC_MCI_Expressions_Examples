This script works in the Calculated Dimension in SFMC Intelligence Advanced. To add a Custom Dimension, your environment needs to have Intelligence Advanced enabled. This will not work if you are just using Datorama Basic, the low end version of Intelligence Reports that comes with SFMC Engagement.

This Calculated Dimension will become available when creating a Intelligence Report. I am using the [Email_Content_Name] to break out the emails into different categories based on keywords in the field name.

Navigate to: Setup > Calculated Dimensions > Create Calculated Dimension

Here is the fake MCI javascript format to use:

~~~
if(([Email_Content_Name]) contains 'Executive Summary') 
{ return 'Executive Summary'; }

else if(([Email_Content_Name]) contains 'Eid' 
  or ([Email_Content_Name]) contains 'Ramada') 
{ return 'Holiday'; } 

else if(([Email_Content_Name]) contains 'Seminar') 
{ return 'Seminar'; } 

else if(([Email_Content_Name]) contains 'Webinar') 
{ return 'Webinar'; } 

else if(([Email_Content_Name]) contains 'Savings') 
{ return 'Savings'; } 

else if(([Email_Content_Name]) contains 'Ready to Upgrade') 
{ return 'Ready to Upgrade'; } 

else if(([Email_Content_Name]) contains 'Lead Follow-up') 
{ return 'Lead Follow-up'; } 

else {return 'Other';}
~~~

