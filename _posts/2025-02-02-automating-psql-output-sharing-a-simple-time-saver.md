---
layout: post
title: 'Automating PSQL Output Sharing: A Simple Time-Saver'
date: '2025-02-02 18:29:02 +0530'
categories:
  - Productivity
tags:
  - PostgreSQL
  - Powershell
comments: []
---

![image by freepik](http://gbhat.site/wp-content/uploads/2025/02/2961855-1024x683.jpg)
<div style="text-align: center;">
  <img src="/assets/images/2025-02-02-automating-psql-output-sharing-a-simple-time-saver.jpg" alt="Automating PSQL Output Sharing image" style="max-width: 300px; width: 100%; height: auto; display: block; margin: 0 auto;" />
  <div style="font-size: 0.9em; color: #555; margin-top: 8px;">
    <em>Image by <a href="https://www.freepik.com/free-vector/image-upload-concept-landing-page_5632187.htm#fromView=search&page=1&position=6&uuid=4ec3ec38-c8ee-470d-b414-03c681d492d7&new_detail=true&query=remote+file+sharing">freepik</a></em>
  </div>
</div>

I volunteer for a PostgreSQL-based web application project, mostly helping with databases, CI, and infrastructure side. The legacy version of the application is being phased out, and we have migrated data from MS Acess to the new PostgreSQL. Numerous data inconsistencies have surfaced (still do) during this migration. Since the data can't be fully rewritten in PostgreSQL, it now contains new data as well, we carefully identify and merge only the necessary records.

The application (and PostgreSQL) is deployed in a local Windows Machine in the organization, and as such I can't access remotely. We have setup a shared folder via Google Drive in this machine, so both me (and 1-2 others in the project) + the admin of the Windows Machine - can easily share the data. We also have daily database backups generating dump in this shared folder.

So whenever there is a data fixing needed, I take the db dump (from the Google Drive), restore in my laptop, analyze through it. I get fixed data in Excel sheet, and my goal is to merge it into PostgreSQL and generate the final version of the fixed rows.

I do all the data schema transformation, fixing null values, fixing blanks with appropriate defaults etc. After that I create two types of `.sql` files. I call them as:

- **Patch Execution File**: Contains SQL commands for tasks like backing up tables, checking record counts, and importing data. It's wrapped in a `BEGIN` and `COMMIT` transaction block to ensure safe retries in case of failure. This file is versioned in a GitHub repo.
- **Patch Data File:** Contains actual data rows with `INSERT` or `UPDATE` statements. This file is not versioned (for obvious reason of data security) but shared via Google Drive, hence accessible on the Windows machine.

I share these files with the admin from the organization who executes the SQL patch. Until recently, they manually ran commands in the `psql` shell, sharing screenshots for my review—a tedious process.

Yesterday, it hit me: Why not feed the patch execution file directly to the `psql` command and redirect the output to a log file synced to Google Drive? This simple solution saved time and streamlined the entire process. Any failures are logged and immediately accessible to me.

Here's the PowerShell command we now use:

```powershell
$SqlFile = "D:/infra-repo/sql/01-profile-fix-patch-part-1-apply.sql"
$LogFile = "D:/shared_folder/tasks/0x-profile-fix/feb01-patch-files/01-profile-fix-patch-part-1-apply.log"

cd 'C:\Program Files\PostgreSQL\15\bin'
./psql.exe -h localhost -d <database> -U <user> -f $SqlFile -W *> $LogFile 2>&1
```

Since implementing this, patch executions have become simple, efficient, and fail-safe.