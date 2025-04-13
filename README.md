# CBT789
Converted to GitHub via [cbt2git](https://github.com/wizardofzos/cbt2git)

This is still a work in progress. GitHub repos will be deleted and created during this period...

```
//***FILE 789 is from Al Ferguson and contains a batch job to       *   FILE 789
//*           automate and run IBM's SCRT (Sub-Capacity             *   FILE 789
//*           Reporting Tool) report every month automatically,     *   FILE 789
//*           and to email the result to IBM.  This will help       *   FILE 789
//*           all of you who have to do this, and use a person      *   FILE 789
//*           to perform all the operations manually.               *   FILE 789
//*                                                                 *   FILE 789
//*           email: Al.Ferguson@sccompanies.com                    *   FILE 789
//*                                                                 *   FILE 789
//*   See member $$NOTE02 for update information.                   *   FILE 789
//*                                                                 *   FILE 789
//*   Description ---                                               *   FILE 789
//*                                                                 *   FILE 789
//*   I have been working on a batch JOB to automate the            *   FILE 789
//*   sending of our Monthly SCRT Report (Sub-Capacity              *   FILE 789
//*   Reporting Tool) to IBM for Sub-Capacity Licensing via         *   FILE 789
//*   eMail. It uses:                                               *   FILE 789
//*                                                                 *   FILE 789
//*   o CBT GDG Copy Utility (File 482)                             *   FILE 789
//*   o A REXX I wrote to Build the IFASMFDP PARMs to               *   FILE 789
//*     get just last months MULC Records (runs under               *   FILE 789
//*     IRXJCL).                                                    *   FILE 789
//*   o IBM's SCRTTOOL (see                                         *   FILE 789
//*     http://www-03.ibm.com/servers/eserver/zseries/swprice/scrt/ *   FILE 789
//*   o A RXSOCKET API based REXX I wrote to submit the             *   FILE 789
//*     report as a MIME attachment to IBM's LMS eMail              *   FILE 789
//*     process (runs under IRXJCL).                                *   FILE 789
//*   o A REXX to do date manipulation, based of a REXX &           *   FILE 789
//*     Algorithms by David A. Cromley (A System Programmer         *   FILE 789
//*     Journal article from early 1990's).                         *   FILE 789
//*                                                                 *   FILE 789
//*   I also have the following JCL for this process:               *   FILE 789
//*                                                                 *   FILE 789
//*   o The entire JOB (6 STEPs + 1 per Image with MULC             *   FILE 789
//*     Records you need to process)                                *   FILE 789
//*   o Sample PARMs for my REXX EXECs.                             *   FILE 789
//*   o Sample PARMs for SCRT Tool (though each shop                *   FILE 789
//*     update these to reflect their environment)                  *   FILE 789
//*   o Sample JOB to LINKEDIT the SCRTTOOL (IBM gives              *   FILE 789
//*     you an inline LinkEdit-Go JOB)                              *   FILE 789
//*                                                                 *   FILE 789
//*   We schedule this JOB to run on the 2nd day of the month,      *   FILE 789
//*   early in the morning.  (This is the earliest IBM is ready     *   FILE 789
//*   to accept these reports).  It automatically sends the         *   FILE 789
//*   SCRT Tool Report to IBM each month.  IBM's suggested way      *   FILE 789
//*   to accomplish this requires a number of manual steps          *   FILE 789
//*   (create the report, download to your PC, create an email,     *   FILE 789
//*   attach the report, and send).  Using our process I do not     *   FILE 789
//*   forget and can go on vacation during the beginning of the     *   FILE 789
//*   month (with IBM's manual process, this could cause fines      *   FILE 789
//*   if we miss getting the report to them on time).               *   FILE 789
//*                                                                 *   FILE 789
//*   Since IBM "improved" its eMail process, it has gotten         *   FILE 789
//*   very picky.  It took 3 months to get this working again       *   FILE 789
//*   (IBM has a number of not so well documented                   *   FILE 789
//*   requirements for this process. They also gave little          *   FILE 789
//*   information to help us figure out why it was not being        *   FILE 789
//*   accepted by the new process). This version works with         *   FILE 789
//*   the new system which assumes your IBM Account Name is         *   FILE 789
//*   also your email address and is 32 or less characters in       *   FILE 789
//*   total. For those using Sub-Capacity Licensing, this may       *   FILE 789
//*   be quite useful (and allow them to keep some more of          *   FILE 789
//*   their hair, vs. trying to figure this out on their            *   FILE 789
//*   own).                                                         *   FILE 789
//*                                                                 *   FILE 789
//*   In the process of creating this I wrote a generic             *   FILE 789
//*   RXSOCKET API base REXX to do eMail with MIME                  *   FILE 789
//*   attachments. I also used this to test the SMTP Server         *   FILE 789
//*   and adjust its configuration (getting it to work,             *   FILE 789
//*   securing it, and tuning logging). This REXX runs under        *   FILE 789
//*   IRXJCL and handles the following MIME Types:                  *   FILE 789
//*                                                                 *   FILE 789
//*   The last Content-Type requires access to the Leland           *   FILE 789
//*   Lucius's ENCODE64 REXX Function from                          *   FILE 789
//*   http://www.homerow.net/asm/index.htm (I believe it is         *   FILE 789
//*   also part of his XMITIP).  I also have a sample JOB to        *   FILE 789
//*   run this REXX adding a couple of attachments. This was        *   FILE 789
//*   an interesting programming exercise in socket                 *   FILE 789
//*   Programming, SMTP socket programming, and SMTP header         *   FILE 789
//*   coding.  I have not seen a RXSOCKET API REXX that             *   FILE 789
//*   covered all of this, so it may be of interest to others       *   FILE 789
//*   for this reason.  This REXX works under:                      *   FILE 789
//*                                                                 *   FILE 789
//*   o IRXJCL with pre-allocated files (TSO is not                 *   FILE 789
//*     required)                                                   *   FILE 789
//*   o TSO with pre-allocated files                                *   FILE 789
//*   o A REXX or CList running under TSO, used to build            *   FILE 789
//*     and pre-allocate the files.                                 *   FILE 789
//*                                                                 *   FILE 789
```
