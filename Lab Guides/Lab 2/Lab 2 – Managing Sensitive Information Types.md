# Lab 2 – Managing Sensitive Information Types​

## Objective:

Contoso Ltd. previously had issues with employees accidentally sending
out personal information from customers when working on support tickets
in the ticketing solution.

To educate users in the future, a custom sensitive information type is
required to identify employee IDs in emails and documents, which consist
of three uppercase characters and six numbers, using Sensitive info
types. To lower the false positive rate, the keywords "Employee" and
"IDs" will be used.

In this Lab you will create:

- a new custom sensitive information type

- a database for EDM-based classification

- keyword dictionary

## Exercise 1 – Creating Custom Sensitive Information Types

In this exercise, you will use the **Security & Compliance Center
PowerShell** module to create a new custom sensitive information type
that recognizes the pattern of employee IDs near the keywords "Employee"
and "ID".

1.  In **Microsoft Edge**, open a **New InPrivate Window**, navigate
    to **+++**https://**purview**.microsoft.com**+++** and log in as
    **Patti Fernandez** using the
    username **PattiF@WWLxXXXXXX.onmicrosoft.com** and the User Password
    given on your resources tab.

2.  From the left navigation, select **Solutions** \> **Data Loss
    Prevention**.

![](./media/image1.png)

3.  Select **Classifiers** from the left pane. Select **Sensitive info
    types** from the sub-navigation pane. Select **+Create sensitive
    info type** to open the wizard for a new sensitive information type.

![A screenshot of a computer Description automatically
generated](./media/image2.png)

4.  On the **Name your sensitive info type** page, enter the following
    information:

    - **Name**: **+++Contoso Employee IDs+++**

    - **Description**: **+++Pattern for Contosoemployee IDs+++.**

5.  Select **Next**.

![Graphical user interface, application Description automatically
generated](./media/image3.png)

6.  On the **Define patterns for this sensitive info type** page,
    select **Create pattern**.

![A screenshot of a computer Description automatically
generated](./media/image4.png)

7.  In the right-side **New pattern** pane, select **Add primary
    element** and select **Regular expression**.

![Graphical user interface, application, Teams Description automatically
generated](./media/image5.png)

8.  In the new right-side pane **Add a regular expression**, enter the
    following:

    - **ID**: **+++Contoso IDs+++**

    - **Regular expression**: **+++\s\[A-Z\]{3}\[0-9\]{6}\s+++**

    - Select **String match**

9.  Select **Done**.

![Graphical user interface, application Description automatically
generated](./media/image6.png)

10. In the right-side **New pattern** pane again, below **Supporting
    elements**, select **+ Add supporting elements or group of
    elements** drop-down menu and select **Keyword list**.

![Graphical user interface, application Description automatically
generated](./media/image7.png)

11. In the new right-side pane **Add a keyword list**, enter the
    following:

    - **ID**: **+++Employee ID keywords+++**

    - **Case insensitive**:

**+++Employee**

**ID+++**

12. Select the radial for ***Word match*** under the **Case
    Sensitive** field

13. Select **Done**.

![Graphical user interface, text, application Description automatically
generated](./media/image8.png)

14. In the New pattern windows decrease the **Character
    proximity** value to ***100*** characters.

![Graphical user interface, text, application Description automatically
generated](./media/image9.png)

15. Select the **Create** button.

16. Back on the **Define patterns for this sensitive info type** page
    select **Next**.

![Graphical user interface, text, application, Teams Description
automatically generated](./media/image10.png)

17. On the **Choose the recommended confidence level to show in
    compliance policies** page, use the default value and
    select **Next**.

![BrokenImage](./media/image11.png)

18. On the **Review settings and finish** page review the settings and
    select **Create**. When successfully created select **Done**.

![Graphical user interface, text, application Description automatically
generated](./media/image12.png)

19. Leave the browser window open.

You have successfully created a new sensitive information type to
identify employee IDs in the pattern of three uppercase characters, six
numbers, and the keywords 'Employee' or 'IDs' within a range of 100
characters.

## Exercise 2 – Creating EDM-based classification information type

As an extra search pattern, you will create an EDM-based classification
with a database schema of employee data. The database source file will
be formatted with the following data fields of employees: Name,
Birthdate, StreetAddress, and EmployeeID.

1.  Select **Solutions** \> **Data Loss Prevention** \> **Classifiers**,
    navigate to **EDM classifiers**, switch off **New EDM experience**,
    and from EDM Schema, select **+ Create EDM schema** to create a new
    schema definition.

![A screenshot of a computer Description automatically
generated](./media/image13.png)

2.  In the **Name** field, enter **+++employeedb+++**.

3.  In the **Description** field,
    enter **+++Employee Database schema.+++**.

4.  Enable **Ignore delimiters and punctuation for all schema fields**.

![A screenshot of a computer Description automatically
generated](./media/image14.png)

5.  Click the dropdown for **Choose delimiters and punctuation to
    ignore** and select **Hyphen**, **Period**, **Space**, **Open
    parenthesis** and **Close parenthesis**.

![Graphical user interface, application Description automatically
generated](./media/image15.png)

6.  In the first Schema field name, enter **+++Name+++** and mark
    the **Field is searchable** box.

7.  Select **+ Add schema data field** from the lower end.

![BrokenImage](./media/image16.png)

8.  In **Schema field name**, below **Schema field \#2**,
    enter **+++Birthdate+++**.

9.  Select **+ Add schema data field** from the lower end again.

10. In **Schema field name**, below **Schema field \#3**,
    enter **+++StreetAddress+++**.

11. Select **+ Add schema data field** from the lower end a last time.

12. In **Schema field name**, below **Schema field \#4**,
    enter **+++EmployeeID+++**.

13. Select **Field is searchable**.

14. Select **Save**.

![Graphical user interface, application Description automatically
generated](./media/image17.png)

15. Select **EDM sensitive info types** from the left pane and
    select **+ Create EDM sensitive info type** to open the **EDM rule
    package** wizard.

![](./media/image18.png)

16. On the **Define data store schema** page, select **Choose an
    existing EDM schema**.

![Graphical user interface, application Description automatically
generated](./media/image19.png)

17. Select **employeedb** and select **Add**.

![Graphical user interface, text, application Description automatically
generated](./media/image20.png)

18. Review the data store schema and select **Next**.

![Graphical user interface, application Description automatically
generated](./media/image21.png)

19. On the **Define patterns for this EDM sensitive info type** page,
    select **+ Create pattern**.

![Graphical user interface, application Description automatically
generated](./media/image22.png)

20. On the **New pattern** pane on the right-side, in the **Primary
    element** field, select ***EmployeeID***.

21. Below **Primary element's sensitive info type**, select **Choose
    sensitive info type**.

![A screenshot of a pattern Description automatically
generated](./media/image23.png)

22. In the **Search** bar, enter ***Contoso*** and press the enter key.

23. Select **Contoso Employee IDs** and select **Done**.

24. Select **Done**.

![A screenshot of a computer Description automatically
generated](./media/image24.png)

25. Select **Next** in the *Define patterns for this EDM sensitive info
    type* screen.

![Graphical user interface, text, application Description automatically
generated](./media/image25.png)

26. In the **Choose the recommended confidence level and character
    proximity** let the default value persist and select **Next**.

![Graphical user interface, text, application, Word Description
automatically generated](./media/image26.png)

27. In the **Name and describe your EDM sensitive info type** page,
    enter **+++Contoso Employee EDM+++** for the name.

28. In the **Description for admins** field, enter **+++EDM-based
    sensitive information type for employee personal information.+++**.
    Select **Next.**

![Graphical user interface, text, application Description automatically
generated](./media/image27.png)

29. Review the settings and select **Submit**.

![Graphical user interface, application Description automatically
generated](./media/image28.png)

30. On the **Your EDM sensitive info type was created** page,
    select **Done**.

![A screenshot of a computer Description automatically
generated](./media/image29.png)

31. Leave the browser open with the Microsoft Purview portal.

You have successfully created a new EDM-based classification sensitive
information type for identifying employee data from a database file
source.

## Exercise 3 – Creating EDM-based classification data source

To associate the EDM-based classification with a database containing
sensitive data, hashing and uploading the actual data for the sensitive
information type via the EDM Upload Agent tool is required next.

1.  In **Microsoft Edge**, navigate
    to **+++**https://go.microsoft.com/fwlink/?linkid=2088639**+++** to
    access the EDM download agent.

2.  Select **Run** to download and install the tool.

![BrokenImage](./media/image30.png)

3.  In the **Microsoft Exact Data Match Upload Agent Setup** wizard,
    select **Next**.

    - Select **I accept the terms in the License Agreement** and
      select **Next**.

    - Do not change the default **Destination Folder** path and
      select **Next**.

    - Select **Install** to perform the installation.

    - When the **User Account Control** window opens, select **Yes**.

    - If asked to log in, log in via **Patti’s** account.

    - When the installation finishes, select **Finish**.

    - Select the Windows symbol in the lower left to open the start
      menu, enter **Notepad** and select **Notepad** from the start
      menu.

    - Enter the following text to the first line in the notepad window:

**+++Name,Birthdate,StreetAddress,EmployeeID**

**Patti Fernandez,01.06.1980,1Main Street,CSO123456**

**Christie Cline,31.01.1985,2Secondary Street,CSO654321+++**

4.  Select File and Save As: **+++EmployeeData.csv+++**

5.  Select the dropdown at **Save as type:** and select **All Files
    (*.*)**.

6.  Select the dropdown at **Encoding:** and select **UTF-8** and
    select **Save**.

![BrokenImage](./media/image31.png)

7.  Close the Notepad window.

8.  Select the windows symbol in the taskbar with the right mouse button
    and select **Windows PowerShell (Admin)** and run as administrator.

![BrokenImage](./media/image32.png)

9.  When the **User Account Control** window opens, select **Yes**.

10. Navigate to the EDM Upload Agent directory:

**+++cd "C:\Program Files\Microsoft\EdmUploadAgent"+++**

![Text Description automatically generated](./media/image33.png)

11. Authorize with your Account to upload the database to your tenant by
    running the following cmdlet:

**+++.\EdmUploadAgent.exe /Authorize+++**

![BrokenImage](./media/image34.png)

12. When the **Pick an account** window is displayed, log in as **Patti
    Fernandez** using the username **PattiF@WWLxXXXXXX.onmicrosoft.com**
    and the User Password given on your resources tab. (Or the new
    password you reset.)

Note: For the next steps, please make sure that the path of the files
resembles the path in your VM. It may be different than the instructions
or the screenshots. In such case please change the path of your file in
the commands accordingly.

13. Download the database schema definition of the EDM-based
    classification sensitive information type by running the following
    script in PowerShell:

**+++.\EdmUploadAgent.exe /SaveSchema /DataStoreNameemployeedb /OutputDir
”C:\Users\Admin\Documents\\+++**

**Note**: If the last command fails, it possibly takes more time until
the **EDM_DataUploaders** group membership is applied. It can take up to
one hour until it is possible to download the schema file. If it fails
proceed to the next task and return to this step later. Or check the
path the documents folder on your VM.

![BrokenImage](./media/image35.png)

14. Hash the database file and upload it to the EDM-based classification
    sensitive information type by running the following script in
    PowerShell:

**+++.\EdmUploadAgent.exe /UploadData/DataStoreName employeedb /DataFileC:\Users\Admin\Documents\EmployeeData.csv /HashLocation C:\Users\Admin\Documents\\/SchemaC:\Users\Admin\Documents\employeedb.xml+++**

![BrokenImage](./media/image36.png)

**Note:** If you get the following errors

Error Type: System.IO.FileNotFoundException

Error Message: Unable to find the specified file.

Check the path where you saved the file EmployeeData.csv

![Text Description automatically generated](./media/image37.png)

15. Check the upload progress until the state changes to completed then
    run the following PowerShell command:

**+++.\EdmUploadAgent.exe /GetSession /DataStoreNameemployeedb+++**

![BrokenImage](./media/image38.png)

You have successfully hashed and uploaded a database file for a
EDM-based classification sensitive information type.

## Exercise 4 – Creating Keyword Dictionary

Several violations of personal information leakage happened when users
sent out emails after colleagues reported on sick leave. When that
happened the reason for illness or disease was sent out. We do not want
that to happen.

1.  In **Microsoft Edge**, open a **New InPrivate Window**, navigate
    to **+++https://purview.microsoft.com+++** and log in as **Patti
    Fernandez** using the username **PattiF@WWLxXXXXXX.onmicrosoft.com**
    and the User Password given on your resources tab.

2.  From the left navigation, select **Solutions** \> **Data Loss
    Prevention**.

![A screenshot of a computer Description automatically
generated](./media/image1.png)

3.  Select **Classifiers** from the left pane. Select **Sensitive info
    types** from the sub-navigation pane. Select **+Create sensitive
    info type** to open the wizard for a new sensitive information type.

![A screenshot of a computer Description automatically
generated](./media/image2.png)

4.  On the **Name your sensitive info type** page, enter the following:

    - Name: **+++Contoso Diseases List+++**

    - Description: **+++List of possible diseases of employees.+++**

![Graphical user interface, application, Teams Description automatically
generated](./media/image39.png)

5.  Select **Next**.

6.  On the **Define patterns for this sensitive info type** page,
    select **+ Create pattern**.

![Graphical user interface, application, Teams Description automatically
generated](./media/image40.png)

7.  Select the dropdown field below **Primary element** and
    select **Keyword dictionary**.

![Graphical user interface, application Description automatically
generated](./media/image41.png)

8.  In the **Add a keyword dictionary** page enter the
    name **+++*Diseases Dictionary*+++**.

9.  In the **Keywords** area enter the following keywords, each into a
    separate line:

**+++flu**

**influenza**

**cold**

**bronchitis**

**otitis+++**

![BrokenImage](./media/image42.png)

10. Select **Done**.

11. Below **Supporting elements**, select **+ Add supporting elements or
    group of elements** drop-down and select **keyword list** to add
    additional support for the keyword dictionary.

![Graphical user interface, application Description automatically
generated](./media/image43.png)

12. In the **Add a keyword list** page enter **Employee absence** in
    the **ID** field. In the **Case insensitive** box, enter the
    following keywords, each into a separate line:

**+++employee**

**absence**

**reason+++**

![Graphical user interface, application Description automatically
generated](./media/image44.png)

13. Select **Done**.

14. In the **New pattern** page, review the configuration and
    select **Create**.

![Graphical user interface, application Description automatically
generated](./media/image45.png)

15. In the **Define patterns for this sensitive info
    type** select **Next**.

![Graphical user interface, application, Teams Description automatically
generated](./media/image46.png)

16. In the **Choose the recommended confidence level to show in
    compliance policies** let the default value persist and
    select **Next**.

![A screenshot of a computer Description automatically
generated](./media/image47.png)

17. In the **Review settings and finish** page, review your settings and
    select **Create**. When the process is complete select **Done**.

![BrokenImage](./media/image48.png)

18. Leave the browser window in the Microsoft Purview portal open.

You have successfully created a new sensitive information type based on
a keyword dictionary and added more keywords to decrease the false
positive rate. Proceed with the next task.

## Exercise 5 – Working with custom Sensitive Information Types

Custom Sensitive information types should always be tested before using
them in policies otherwise data loss or leakage may occur due to a
malfunctioning custom search pattern.

1.  Select the Windows symbol in the lower left to open the start menu,
    enter **Notepad** and select **Notepad** from the start menu.

2.  Enter the following text to the notepad window:

**+++Employee Patti Fernandez EMP123456 is on absence because of the
flu/influenza+++**

3.  Select **File** and Save As **SickTestData** and select **Save**.

4.  Close the Notepad window.

5.  In **Microsoft Edge**, the Microsoft Purview portal tab should still
    be open. If so, select it and proceed to the next step. If you
    closed it, then in a new tab, navigate
    to **+++https://purview.microsoft.com+++**. Log in as **Patti
    Fernandez** using the username **PattiF@WWLxXXXXXX.onmicrosoft.com**
    and the User Password given on your resources tab.

6.  In the left navigation pane select **Solutions** \> **Data Loss
    Prevention**, then select the **Sensitive info types** under
    **Classifiers** . In the **Search** box from the upper right side
    and enter ***Contoso*** and press **Enter**. Select **Contoso
    Employee IDs** to open the right side pane.

![A screenshot of a computer Description automatically
generated](./media/image49.png)

7.  Select **Test** from the right-side pane.

![A screenshot of a computer Description automatically
generated](./media/image50.png)

8.  On the **Upload file to test** page, select **Upload file**.

![BrokenImage](./media/image51.png)

9.  Select **Documents** from the left pane, select the file with the
    name **SickTestData** and select **Open**.

![Graphical user interface, text, application Description automatically
generated](./media/image52.png)

10. Select **Test** to start the analysis.

![Graphical user interface, text, application Description automatically
generated](./media/image53.png)

11. On the **Match results** page, review the found match.

![BrokenImage](./media/image54.png)

12. Select **Finish** and close the test page by clicking
    the **X** button.

![Graphical user interface, text, application Description automatically
generated](./media/image55.png)

13. Back on the **Data classification** page, select the Sensitive
    Information Type with the name **Contoso Diseases** **List**.

14. In the right side pane, select **Test**.

![BrokenImage](./media/image56.png)

15. On the **Upload file to test** page, select **Upload file**.

![BrokenImage](./media/image57.png)

16. Select **Documents** from the left pane, select the file with the
    name *SickTestData* and select **Open**.

17. Select **Test** to start the analysis.

![Graphical user interface, text, application Description automatically
generated](./media/image58.png)

18. On the **Match results** page, review the found match. When done
    review select **Finish**.

![Graphical user interface, application Description automatically
generated](./media/image59.png)

## Summary:

You have successfully tested the two custom sensitive information types
and validated the search pattern recognizes the desired patterns. You
have finished the creation of sensitive information types and can
proceed with the next exercise.
