# Snackbars

A snackbar is a small notification (that gives feedback about an action without
interrupting the user's work.) In this project, snackbars use Sonner through the
shadcn/ui `Toaster` component.

## Position

I choose the top center because in our case the information which it contained wasn't anyting which user have to click on. If it 
would be a clickable popup/modal we need to put it closer to user's finger so he can reach it easyer (in bottom of the UI).

Un clickable:
[example for center]

Clickable
[example for bottom]

Where it should not be:
[Akira] In our case we had a home & other action buttons in the top left. So if we make the snackbar appear there, it 
would require us to do extra work buy making a close button + cluttering the UI for the user.

[Akira] For the websites which have a chat button in the right bottom, the same rules as above works.

[Akira] Consider all of the pages, Consistency
[Akira] You should make research of the projec, take a look at all of it's pages and use the unused space in the desktop. In mobile you dont have this much space.

The application displays snackbars at the **top center** of the screen. One shared
`Toaster` in [`App.tsx`](../frontend/src/App.tsx) keeps their position consistent
across pages:

Snackbars appear without replacing the page or requiring a dialog to be dismissed.
The close button lets users dismiss them manually.

## Content

[Akira] The output should be short and direct. This depend on the durration.

Snackbar content, from actuall side, shorter message, shorter duration + longer, a bit longer duraiton
[example]
[exmaple]

[Akira] Colors. Use green for success. Use red for failure. 

Each message briefly describes the result of an action. For example, adding a task
shows “Task added successfully.” Profile actions also confirm when a skill,
strength, job, or certificate has been added or updated.

Skill creation and editing also show error notifications when the request fails.
They display the error's message when available, with a fallback such as
“Could not update the skill.”

Success and error notifications have distinct icons and colors. Their text explains
the outcome, so color is not the only way to understand the message.

## Duration

[Akira] Should not be too short and not too long either. Longer than 1.8 seconds and not longer than 5-6-7
seconds.

[Akira] We should use popup or modal, if we need user's action. Because snackbar will disappear. We use snackbar for optional
or non action required stuff

Example form other wbsite for howl ong do the show the snackbar:
[exmaple]


The project does not set a custom duration, so ordinary success and error
notifications use the installed Sonner version's default of **4,000 milliseconds
(4 seconds)**. This is the automatic dismissal timer, rather than a guarantee that
every notification disappears exactly four seconds after appearing; interaction
can pause the timer.

A duration can be set for an individual notification in milliseconds. For example,
this would keep a notification visible for six seconds before automatic dismissal,
unless its timer is paused or the user closes it:

This example illustrates an optional override; the current project uses the default.