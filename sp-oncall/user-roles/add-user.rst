.. _add-user:

************************************************************************
Add or remove users
************************************************************************

.. meta::
   :description: How to add or remove users from Splunk On-Call.



In order to add or delete users in Splunk On-Call, you must either have the Global Admin role for global add and remove permissions or the Team Admin role for team-specific add and remove permissions.

Add users
=================

You can add users to Splunk On-Call, to a team, or to a shift.

Invite users to Splunk On-Call
-------------------------------------

- You can invite users to Splunk On-Call by using the public API. For details, see :new-page:`User API <https://portal.victorops.com/public/api-docs.html?_ga=2.169602981.562369111.1519752971-1195437206.1519752971#/Users>`. To invite users via the API, Global Admin permissions are needed. Global admins will be able to set the username when inviting users through API.
- You can invite users on the :guilabel:`User` tab by selecting :guilabel:`Invite User`. When inviting users in the web UI, users are invited via their email and are able to create their own username.



Adding a user to a team
-------------------------------

- Global Admins or Team Admins of the team are able to invite users to a team by selecting :guilabel:`Invite User` on the team's page.

Add users to a shift
-------------------------------

- Once a rotation has been created with one or more shifts, users can be added to each shift by selecting the people icon next to the shift's name.

.. note:: Users must be apart of the team before they are able to be added to a shift.

Remove users
------------------

How user replacement is suggested by Splunk On-Call
--------------------------------------------------------------

When deleting a user from a team or organization:

#. Find all the teams the user is part of or teams in which the user took scheduled overrides or manual on-call.
#. For each team:

   #. If the user is not part of on-call rotation or escalation policies in the team, then the user is removed from the team. Otherwise, proceed to the next step.
   #. Look for an admin in the team in this order: Team Admin, Alert Admin, Global Admin, Non-admin.
   #. Users who have mobile devices registered for push notification or verified phone numbers in their profile are given preference.
   #. If there are more than one user resulting from the above two steps, then pick the first user after sorting on username A to Z.
   #. Place the resulting user as replacement for removed user in scheduled overrides, on-call rotations and escalation policies.

#. The replacement user is notified by email. In the email they get a list of rotations, escalation policies that were changed and also are told if any overrides changed.

Manual user selection as replacement for user to be removed
-------------------------------------------------------------------

If the manually selected user for replacement is not part of the team, then the user will be added to the team and replace the removed user in respective on-call rotations and escalation policies.

Removing a user from a shift
-------------------------------

To remove a user on a shift, select the people icon next to the shift name and select the “x” by the user's name.

Removing a User from a team
---------------------------------

On the team's page under the :guilabel:`Users` tab, the delete icon next to the user's name will delete them from the team.

As a fail-safe, when a user is being removed from a team, a replacement user is required to fill any holes the user being removed will open up. If the user being removed is deleted from all shifts they were a part of, the replacement user will act as a wash.

Removing a User from Splunk On-Call
------------------------------------

When removing a user from the platform, first delete them from any shifts and teams the users is apart of. Once the user is removed from any shifts and teams the user is ready to be removed from the platform.

As a fail-safe, when a user is being removed from Splunk On-Call, a replacement user is required to fill any holes the user being removed will open up. If the user being removed was deleted from all shifts and teams, the replacement user will act as a wash.
