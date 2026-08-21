I've been going through Jira to learn the basics of this ticketing system, I've created my own project on Jira along with my first ticket that I will be solving soon.  
<img width="1882" height="697" alt="image" src="https://github.com/user-attachments/assets/6f920c02-aec1-4286-b820-ecd62a9778e2" />

As you can see below, I've updated the ticket by assigning it to myself and transitioning it into in progress.
<img width="1553" height="416" alt="image" src="https://github.com/user-attachments/assets/8d1c7621-c1ec-4783-93ff-2aad8fdbe045" />

## Ticket #001 — User Cannot Log In (Account Lockout)

**Category:** Account Management
**Priority:** High
**Status:** Resolved

### Problem
User reported being unable to log into their computer 
with multiple password attempts failing.

### Environment
DC01 — Active Directory Users and Computers
DC01 — Event Viewer

### Steps Taken
1. Assigned ticket and changed status to In Progress in Jira
2. Checked Jane Smith's account in Active Directory — 
   found account was locked out
3. Verified in Event Viewer — found multiple Event ID 
   4625 failed logon attempts
4. Unlocked account in Active Directory
5. Reset password and enabled "must change at next logon"
6. Verified fix by logging into Client01 as jsmith

### Resolution
Account was locked out due to multiple failed login 
attempts. Unlocked account and reset password. User 
was able to log in successfully.

### What I Learned
Always check AD first for account lockouts before 
assuming it's a password issue. Event Viewer confirms 
how many attempts were made and from which machine.

Below is the ticket updated showing that it was resolved.
<img width="988" height="503" alt="image" src="https://github.com/user-attachments/assets/1eac35b5-d84e-46a9-9e08-eee22558bb38" />

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------

TICKET #002
Priority: Medium
Reporter: Mike Jones (Sales)
Type: Service Request

I've created a new ticket that I've assigned to me on jira as seen below, 
<img width="1361" height="196" alt="image" src="https://github.com/user-attachments/assets/00052c95-01e4-474c-af22-11529216f85c" />

## Ticket #002 — User Cannot Log In (Account Expiration)

**Category:** Account Management
**Priority:** Medium
**Status:** Resolved

### Problem
User reported being unable to log in after returning from a two week vacation. Multiple login attempts 
failed despite using correct password.

### Environment
DC01 — Active Directory Users and Computers
DC01 — Event Viewer

### Steps Taken
1. Assigned ticket and changed status to In Progress in Jira
2. Checked Mike Jones account in Active Directory — found account expiration date was set to August 18th which had already passed
3. Verified in Event Viewer — Event ID 4625 confirmed login failures with account expiration as failure reason
4. Updated account expiration date to Never in AD Account tab — Mike is a permanent employee with no need for expiration date
5. Verified fix by logging into Client01 as mjones successfully

### Resolution
Account had expired while user was on vacation. Updated expiration date to Never. User was able to log in successfully.

### What I Learned
Not all login failures are lockouts. Always check the Account tab in AD properties — expiration dates are easy to miss but a common cause of login issues 
especially after employees return from extended leave. Event Viewer Failure Reason field confirms the exact cause of login failures.

Here's me resolving the ticket and adding an internal note for the manager to read and understand why the ticket was closed,
<img width="790" height="763" alt="image" src="https://github.com/user-attachments/assets/92456bef-14a3-40ca-9a09-b665b59e2e66" />

The next ticket I received was an onboarding one,

TICKET #003
Priority: Medium
Reporter: John Doe (IT)
Type: Service Request

"Hey, we just hired a new employee named Sarah Connor who will be joining the Sales team next Monday. Can you set up her account and make sure she has access to everything the Sales team has access to. Her username should be sconnor. Thanks"

Below is the ticket I've created in jira and assigned to myself,
<img width="1342" height="269" alt="image" src="https://github.com/user-attachments/assets/59c67192-4c51-49c6-a7e0-b81f46652cd9" />

## Ticket #003 — New Employee Account Setup (Onboarding)

**Category:** Account Management
**Priority:** Medium
**Status:** Resolved

### Problem
New employee Sarah Connor joining Sales team on Monday needs a domain account set up with access to Sales 
team resources.

### Environment
DC01 — Active Directory Users and Computers

### Steps Taken
1. Assigned ticket and changed status to In Progress in Jira
2. Created new user account in Sales OU with username sconnor
3. Set temporary password with "must change at next logon" enabled for security
4. Created Sales-Team security group in Sales OU
5. Added Sarah Connor to Sales-Team group so she inherits Sales team resource access
6. Verified account on Client01 — password change prompt appeared correctly and user reached desktop 
   successfully after setting new password

### Resolution
New user account created in correct OU with proper group membership. Account verified and ready for 
employee's first day Monday.

### What I Learned
Onboarding tickets aren't just about creating an account — you need to make sure the user is in the 
right OU and the right security groups so they have access to everything their team has from day one. 
A user in the wrong OU or missing from their department group will be missing resources on their first day 
which creates more tickets.

Like before I closed the ticket and left a note of why the ticket was closed for my manager to see.








