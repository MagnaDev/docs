# John Lewis Mainframe

## Instructions

Open the Mainframe executable and wait for it to fully load.

Once it does, type `tso <username>` and press **Right Ctrl** or 
**Numpad Enter**.

!> The Mainframe uses **Right Ctrl** and **Numpad Enter** to execute actions!
    From here on, this will be known as **execute**.

When prompted, enter your password and **execute**. A notification will be 
displayed which can be cleared by issuing another **execute**.

You are now in *File-AID for DB2*. By default, the cursor should be placed after
the `OPTION  ===>` text. If it is not, move the cursor there with the mouse
or navigate with the arrow keys. Type `3.7.3` and **execute**.

On the next screen, ensure that *Criteria Display Format* is equal to `S`
and **execute**.

Place your cursor where it says `=NOTE=` (the top most one), type `d500` and
**execute**. This should leave you with two lines of stars. 

Place your cursor at the top most set of six stars (`******`), type `i550` and 
**execute**. This creates a workspace for SQL to be typed.

Paste (**Ctrl** + **V**) the required SQL or write your own. This time, press
**F3** to continue, followed by **execute**.

On the next screen, ignore all the settings apart from the one labelled *DSN
Qualifier*. If this shows as `*JOINTAB` then you must specify your own 8
character qualifier and then **execute**.

!> The *DSN Qualifier* can be anything up to 8 characters. You must remember 
    what it is set to as you need it for the FTP process later.

After this, **execute** on the next two screens and *EXTRACT IN PROGRESS* should
appear at the bottom of the screen. Now just wait for the *Extract Summary 
Report* to display and you are done.

In order to retrieve the extract, you have to use the 
[FTP CLI](legacy_reporting/ftp_cli ':target=_blank').

To exit the Mainframe, keep pressing **F3** until you are back at original 
screen. It is now safe to close the program.




