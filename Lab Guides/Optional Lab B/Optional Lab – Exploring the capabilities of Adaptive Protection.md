# Optional Lab B – Exploring the capabilities of Adaptive Protection

## Exercise 1 – Setting up Adaptive Protection

### Task 1 – Setting up risk levels for Adaptive Protection

1.  In Microsoft Edge, open a New InPrivate Window, navigate
    to **+++https://purview.microsoft.com+++** and log in using the
    admin tenant.

2.  From the navigation bar, go to **Solutions** \> **Insider risk**
    **management**.

![](./media/image1.png)

3.  From the sub-navigation, select **Adaptive Protection (Preview)**.

![A screenshot of a computer Description automatically
generated](./media/image2.png)

4.  Since we used the quick start option while enabling **Adaptive
    Protection**, we can see 2 DLP policies created.

![A screenshot of a computer Description automatically
generated](./media/image3.png)

5.  Now click on **Risk levels for Adaptive Protection** from the
    submenu and from the drop down select **Data leaks by a user**.

![BrokenImage](./media/image4.png)

6.  Under **Define conditions for risk levels**, select **User performs
    at least 3 data exfiltration activities,
    each…** for **Elevated** risk. Select **User performs at least 2
    data exfiltration activities, each… **for **Moderate** risk.
    **Select User performs at least 1 data exfiltration activities,
    each…** for **Minor** risk. Then click **Save**.

![BrokenImage](./media/image5.png)

7.  Similarly, you can customise the conditions for all the available
    policy under Insider risk management.

8.  Now we can customise the DLP policy for each level.

Task 2 – Exploring Default DLP policies for each of the risk levels of
Adaptive Protection

1.  Under Adaptive Protection, select DLP Polices and select Adaptive
    Protection Policy for Endpoint DLP.

![BrokenImage](./media/image6.png)

2.  Select **Edit**.

![A screenshot of a computer screen Description automatically generated
with medium confidence](./media/image7.png)

3.  Click on Next till you reach **Customize advanced DLP rules**.

![A screenshot of a computer Description automatically
generated](./media/image8.png)

4.  Check the rules and the conditions made for each level of risk.
    Click **Next**.

5.  On the **Policy mode** page select the radio button near **Turn it
    on right away**. Click **Next**.

![A screenshot of a computer Description automatically
generated](./media/image9.png)

6.  Select **Submit**.

![A screenshot of a computer Description automatically
generated](./media/image9.png)

7.  Repeat the steps to enable the Adaptive Protection Policy for Teams
    and Exchange DLP.

8.  We will not create any rules or policy as of now, but you can
    explore various available option after you complete the lab.
