# GRT Leadtime

## Prerequisites

* Comfortable with the [John Lewis Mainframe][0] and the [FTP CLI][1].

## Instructions

To begin, two text files need to be retrieved. One from the 
[John Lewis Mainframe][0] and the other from the KiSoft database.

### John Lewis Mainframe File Retrieval

This text file has to be extracted via the following SQL in the John Lewis 
Mainframe. Replace the date placeholders with the Sunday before the previous 
and the previous Saturday respectively.

``` sql
select
  num, jou_num_iss, jou_num_dest, jou_num_rec,
  date(issstamp) issdate, date(recstamp) recdate,
  replace(char(date(recstamp)), '.', '/') || ' ' ||
  replace(char(time(recstamp)), '.', ':') rectimestamp
from
  ldba.tcon000
where
  jou_num_iss in (16, 18, 51, 79)
  and date(recstamp) between 'dd.mm.yyyy' and 'dd.mm.yyyy'
```

Once the extract is complete, use the [FTP CLI][1] to retrieve the text file.

``` bash
get 'sv0849.tcon000.unload' C:/Downloads/GRSTrack/grt_host.txt
```

### KiSoft Database File Retrieval

This text file is emailed in a compressed archive format every Sunday evening.
If you require to be added to this mailing list, please contact Nick.

Unzip the content of the archive to `C:/Downloads/GRSTrack/grt_kisoft.txt`.

### Report Generation

Now that both text files have been retrieved and placed in the correct file 
location, the GRT Leadtime report can be generated.

Locate and open the Microsoft Access database 
`W:\Public\Implementation Team\11. GRT Investigation\grt_v1.5.mdb`.

Click **Import Data** and wait for the import to finish. Click **OK** when the
info box appears.

Next, click **All DC** and wait for the report to generate. Save the report 
with the name set as `dc_leadtimes_yyyymmdd.pdf` replacing the placeholder date
with today's date. Save it in 
`W:\Public\Implementation Team\11. GRT Investigation\v1-5 pdf\`.

Attach the generated pdf file to an email titled `DC to Branch Leadtime Report (
dd/mm/yyyy - dd/mm/yyyy)` using the dates that were used in the Mainframe 
extract.

If you don't have the mailing list, please contact Nick.

[0]: legacy_reporting/mainframe
[1]: legacy_reporting/ftp_cli