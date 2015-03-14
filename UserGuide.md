# Google Email Uploader User Guide #

The Google Email Uploader is a desktop utility for Microsoft Windows that uploads email from other desktop email programs (like Microsoft Outlook) into your Google Apps mailbox. The Email Uploader preserves information like sent dates and sender/recipient data, as well as folder structure or other organizational tagging devices used by the other email program.

If you want to import mail from another web-based mail application, or mail that's stored on mail server,  [Gmail's Mail Fetcher](http://mail.google.com/support/bin/answer.py?hl=en&answer=21288) tool may be a better option.

The Email Uploader is Apache 2.0 licensed open source software, and is governed by the terms of the included license file. This also means you may modify the tool to better suit your needs.

## Contents: ##

  * Requirements
  * Email Program Compatibility
  * Importing Your Mail
  * Troubleshooting

## Requirements ##

  * You must have a Google Apps account for one of the following Google Apps editions:
    * Google Apps Premier Edition
    * Google Apps Education Edition
    * Google Apps Partner Edition
  * Your domain administrator must enable end user migration in the Google Apps administrator console under the Advanced Settings page.
  * Microsoft .NET 2.0 or higher.  If you do not have .NET 2.0 installed, the installer will install it for you.

## Email Program Compatibility ##

The Email Uploader is compatible with the following email programs:
  * Microsoft Outlook 2002+
  * Microsoft Outlook Express 6.0+
  * Mozilla Thunderbird 1.5+
_Note:_ Windows Mail on Microsoft Windows Vista is not currently supported.

## Importing Your Mail ##

Before opening the Email Uploader, be sure to close all email programs such as Microsoft Outlook, Microsoft Outlook Express, or Mozilla Thunderbird. Having these applications open will interfere with the migration process.

Launch the Email Uploader from your Start Menu or desktop. The Email Uploader is a simple wizard that walks you through the four-step import process.

### Step 1: Sign In ###

Before uploading can begin, you need to identify the Google Apps account you want to import your email into, and verify that you have access to the account. Specify the full qualified email address of your account, for example: **myname@mydomain.com**.

_Note:_ For your security, your password is not written to disk, but only stored in memory while the Email Uploader is running.

### Step 2: Select Mail ###

The Email Uploader displays a list of email programs from which you can import mail. You can choose to either import all mail from one or more of these programs or you can specify a subset to be imported.

To import all mail, select the programs you wish to import from. As you select email programs, the Email Uploader will calculate the amount of email to be imported and the estimated time to completion. When you've selected the programs you want to import from, click "Next".

To specify a subset of mail to be imported, click "Customize".

_Note:_ To include an archived mailbox, you must use the Customize option.

### Step 2a: Customize Email Selection ###

The Customize option lets you select specific folders in each email program to import. For example, you might choose to import everything in your Inbox and in the folders "Home Business" and "Snowboarding" but not mail in the "Spam" folder.

The Email Uploader scans the programs and displays all accounts and folders for each email program. Click on the email program to expand the view, and then click on the folders you want to include in the import. Selected folders are indicated by a check mark.

Most email programs let you create an email archive file (such as an Outlook .PST or Thunderbird .MBOX file) and store it on a backup disk. To include these archived mailboxes, first select the type of email program of the archive you want to import. Then, click the link "Add another mailbox". Use the Browse window to locate and select the archived mailbox file. It will be added to the selected email program.

### Step 3: Create Labels ###

Gmail uses a label feature to organize email, rather than a folder system. Labeling will affect how imported email will appear in your Gmail account, as well as make it easy for you to identify the origin and organization of the email after import is complete.

There are two choices that affect how labeling is applied:
  1. create labels from folder names, and
  1. archive everything.

#### Create labels from folder names: ####

If labels are not created, the following rules are applied:

  1. All imported mail is given a label identifying the source email program, for example: "from Outlook Express".
  1. Mail from a source program's inbox (including subfolders) is placed in the Gmail Inbox.
  1. Mail in a "Deleted mail" or "Trash" folder is migrated into a new Gmail label so that Gmail will not auto-delete the mail. If don't want this mail, you can exclude it using the customize feature in the previous step. If you want to delete it once it is uploaded, just select all emails with this label and 'delete'.

If labels are created, these additional rules are applied:
  1. Mail in certain common folders are placed in Gmail's special folders. These include "Sent Mail", "Drafts", etc.
  1. Mail in other folders is given a label with the name of its folder. Mail in subfolders will have labels for the full path, as well as labels for all parent folders, for example: "work/projects/Tornado".
  1. Mail from a source program's inbox is given an extra label "Inbox/". This extra label allows you to move imported mail out of your Gmail Inbox folder (that is, archive it) but still be able to see all mail imported from your old email inbox.

#### Archive everything: ####

If all mail is archived, imported mail from a source program's inbox is not placed in the Gmail Inbox. If labels are created, this email will still get the "Inbox/" label.

Archived mail can be accessed using Gmails "All Mail" view, viewing it by label, or when it is found as part of a search.

The following example illustrates how original folder locations are converted to labels (assuming the default selection: create labels, do not archive):


| **Folder** | **Label** |
|:-----------|:----------|
| Outlook Express/bob@domain.com/Inbox | Gmail Inbox, Inbox/, from Outlook Express |
| Thunderbird/bob@domain.com/Inbox | Gmail Inbox, Inbox/, from Thunderbird |
| Outlook Express/bob@domain.com/work | work/, from Outlook Express |
| Outlook Express/bob@domain.com/work/contracts | work/contracts/, work/, from Outlook Express |


### Step 4: Import ###

Once you've finalized your import options, click "Import" to begin uploading. The Email Uploader first reads email from your computer and then begins uploading to Google in batches.

If the tool appears to be stuck, have no fear, each individual batch upload may take a minute or two. You can minimize the tool to the system tray and continue working on other tasks.

Once the Email Uploader is completed, it may take up to 48 hours before all your mail is available in your Google Apps mail, depending on load and volume.

### Step 4a: Resolving errors ###

Some email may have failed to upload. Use the Email Uploader troubleshooting tool to see why failures occurred.

## Troubleshooting ##

For additional help, check the Google Email Uploader user support group.

_Problem: Upload finishes quickly without actually uploading mail_

If this is not your first attempt to upload, the Email Uploader may assume you've already uploaded the given mail. To reset the tool, go to your Google Email Uploader data directory and clear out the UserData.xml file (for example: XP - `C:\Documents and Settings\bob\Local Settings\Application Data\Google\GoogleEmailUploader\1.0.0.0\UserData.xml`, Vista - `C:\Users\bob\AppData\Local\Google\GoogleEmailUploader\1.0.0.0\UserData.xml`).

_Problem: The program crashes_

Check the file GoogleEmailUploaderTrace.txt in the Google Email Uploader data directory (for example: WIndows XP - `C:\Documents and Settings\bob\Local Settings\Application Data\Google\GoogleEmailUploader\1.0.0.0\GoogleEmailUploaderTrace.txt`, Vista - `C:\Users\bob\AppData\Local\Google\GoogleEmailUploader\1.0.0.0\GoogleEmailUploaderTrace.txt` ). Check the user support group for similar issues and resolutions.