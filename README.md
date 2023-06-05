# # Security Design Controls 	"Compliant / In-Place
 (Yes / No / NA)"	If "No", targeted timeline to achieve compliance	Comments	Attach Evidence 
Authentication				
Authentication credentials for accessing services external to the application such as database, email server, file server, third party APIs, etc. should be encrypted and stored in a protected location on a trusted system				
Considering the sensitivity of the data / application, users must be authenticated using only the HTTP POST method.				
"Where required, non-temporary passwords must be sent only to the intended users using:
* An encrypted channel such as HTTPS (or)
* In an ecrypted email such as SMTP over HTTPS
"				
"Authentication credentials must meet the Password Strength policy:
# M&S specific policy
"				
Sensitive information such as passwords, Personally Identifiable Information (PII), Non-Public Information (NPI) must be obscured on the user's screen.				
If the number of invalid login attempts are more than three, such accounts must be locked out to prevent brute force attacks				
Password resets should require the same level of stringent security controls as account creation and authentication. 				
Password reset questions should support sufficiently random answers (that cannot be guessed easily)				
For email based resets,  send email only to a pre-registered address with a temporary link/password				
Temporary passwords and links should have a short expiration time (typically < 24 hours)				
First time users with temporary passwords must change their passwords on the first use				
The system should notify users when a password reset occurs				
Prevent password re-use, passwords should be at least one day old before they can be changed, to prevent attacks on password re-use				
Test IDs, issued for the purpose of executing application testing such as performance and product tests, should be set to expire for a period of 4 weeks  or less and must be reactivated after expiration to continue use.				
Default administrator accounts must be renamed to a common user name, if technically possible, and will be used only in case of an emergency. Emergency use of a default administrator account should be treated as a Firefigher ID. Note: Since in UNIX it is not technically possible to create separate administrator accounts or rename the root account, administrators will log into individual none-privileged accounts in the UNIX environment. The use of su (switch-user) or another similar mechanism is mandatory in UNIX environments to maximize accountability with the root account				
User accounts / default user accounts, if dormant or not in use, should be removed 				
The last use (successful or unsuccessful) of a user account should be reported to the user at their next successful login				
Implement monitoring to identify attacks against multiple user accounts, utilizing the same password. This attack pattern is used to bypass standard lockouts, when user IDs can be harvested or guessed (example: Log monitoring implementation like Splunk/Arcsight)				
All vendor-supplied default credentials (User IDs and passwords) must be disabled. For example: Default credentials provided by Oracle database, scott - tiger must not be used for authenticating between the application and database				
Users must be re-authenticated prior to performing critical operations. For example: Edit account information, user profile				
Use Multi-Factor Authentication (MFA) for highly sensitive or high value transactional accounts				
The design should segregate the web application into public and restricted areas using separate folders				
One-way hashsed passwords along with their respective salt values should be stored in the database for verification				
![image](https://github.com/Meghana68/Checklist/assets/94606049/7e62b488-6fcc-44e0-bb97-25f8143ad65f)
