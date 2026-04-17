# Exercise 1: Environment Setup

## Task 1: Create a Fabric workspace

In this task, you create a Fabric workspace. The workspace contains all
the items needed for this lakehouse tutorial, which includes lakehouse,
dataflows, Data Factory pipelines, the notebooks, Power BI datasets, and
reports.

1.  Open your browser, navigate to the address bar, and type or paste
    the following URL: +++https://app.fabric.microsoft.com/+++
    then press the **Enter** button and sign in with your credentials

[TABLE]

2.  In the Workspaces pane, click on **+New workspace** tile

> ![A screenshot of a computer AI-generated content may be
> incorrect.](./media/image1.png)

3.  In the **Create a workspace** pane that appears on the right side,
    enter the following details, and click on the **Apply** button.

[TABLE]

> ![A screenshot of a computer AI-generated content may be
> incorrect.](./media/image2.png)
>
> ![](./media/image3.png)
>
> ![A screenshot of a computer AI-generated content may be
> incorrect.](./media/image4.png)

## Task 2: Create a lakehouse

1.  Create a new lakehouse by clicking on the **+New item** button in
    the navigation bar.

> ![A screenshot of a computer AI-generated content may be
> incorrect.](./media/image5.png)

2.  Filter by, and select, the **+++Lakehouse+++** tile.

> ![A screenshot of a computer AI-generated content may be
> incorrect.](./media/image6.png)

3.  In the **New lakehouse** dialog box, enter **+++IQ_Lakehouse
    +++** in the **Name** field and **unselect** the lakehouses schemas.
    Click on the **Create** button and open the new lakehouse.

> ![A screenshot of a computer AI-generated content may be
> incorrect.](./media/image7.png)
>
> ![A screenshot of a computer AI-generated content may be
> incorrect.](./media/image8.png)

4.  You will see a notification stating **Successfully created SQL
    endpoint**.

> ![A screenshot of a computer AI-generated content may be
> incorrect.](./media/image9.png)

## Task 3: Ingest sample data

1.  In the **IQ_Lakehouse** page, navigate to **Get data in your
    lakehouse** section, and click on **Upload files as shown in the
    below image.**

> ![A screenshot of a computer AI-generated content may be
> incorrect.](./media/image10.png)

2.  On the Upload files tab, click on the folder under the Files

> ![A screenshot of a computer AI-generated content may be
> incorrect.](./media/image11.png)

3.  Browse to **C:\LabFiles\LabFiles** on your VM, then select 
    ** tickets **and** inspections **tables and click
    on **Open** button.

> ![](./media/image12.png)

4.  Then, click on the **Upload** button and close the **Upload
    files** dialog by selecting the **X** icon for the dialog.

> ![](./media/image13.png)
>
> ![](./media/image14.png)

5.  Click and select refresh on the **Files**. The file appear.

> ![](./media/image15.png)

6.  In the **Lakehouse** page, Under the Explorer pane select **Files**.
    Now, hover your mouse over the **inspections.csv** file. Click on
    the horizontal ellipses **(…)** beside **inspections.csv**. Navigate
    and click on **Load Table**, then select **New table**.

> ![](./media/image16.png)
>
> ![](./media/image17.png)

7.  In the **Load file to new table** dialog box, click on
    the **Load** button.

> ![](./media/image18.png)

8.  Now successfully created **DimProducts** table

> ![](./media/image19.png)

9.  Select the **inspections** table to preview the data.

\[!note\]**Note**: You may need to select the **Refresh** button more
than once to preview the data.

> ![](./media/image20.png)

10. Repeat Steps 7 through 9 to push the remaining file into the tables.

![](./media/image21.png)

![](./media/image22.png)

![](./media/image23.png)

![](./media/image24.png)

11. From the left navigation bar, select **Fabric IQ Ontology**.

> ![](./media/image25.png)

# Exercise 2: Building an ontology from OneLake

## Task 1: Create ontology (preview) item

1.  In your Fabric workspace, select **+ New item**. Search for and
    select the **Ontology (preview)** item.

> ![](./media/image26.png)

2.  Enter +++**NetworkOperationsOntology+++** for the **Name** of your
    ontology and select **Create**.

> ![](./media/image27.png)
>
> ** Tip:** Ontology names can include numbers, letters, and
> underscores. Don't use spaces or dashes.

3.  The ontology opens when it's ready.

> ![](./media/image28.png)
>
> Next, create entity types, data bindings, and relationships based on
> data from your lakehouse tables.

## Task 2: Create Entity Types and Data Bindings

> Entity types represent categories of objects in your business domain.
> For this schema, you will create two entity
> types: **Tickets** and **Inspections**.

### 2.1 — Add the Tickets Entity Type

1.  From the top ribbon or the center of the configuration canvas,
    select **Add entity type**.

> ![](./media/image29.png)

2.  Enter +++**Tickets**+++ as the name and select **Add Entity Type**. 

> ![](./media/image30.png)

3.  The **Tickets** entity type appears on the configuration canvas and
    the **Entity type configuration** pane opens.

> ![](./media/image31.png)

4.  Switch to the **Bindings** tab and select **Add data to entity
    type**.

> ![](./media/image32.png)

5.  Choose your data source: a. Select your **Lakehouse** and
    select **Add**. 

> ![](./media/image33.png)

6.  Select the **tickets** table and select **Next**. 

> ![](./media/image34.png)

7.  Configure a **Static** data binding:

- For **Binding type**, keep the default **Static**.

- Under **Bind your properties**, the columns from the tickets table
  populate automatically:

[TABLE]

- Select **Save**.

> ![](./media/image35.png)

8.  Back in the Entity type configuration pane, select **Add entity type
    key**. 

> ![](./media/image36.png)

9.  Select **ticket_id** as the key property and select **Save**.

> ![Tickets entity type key](./media/image37.png)

### 2.2 — Add the Inspections Entity Type

> Follow the same steps as above for the **Inspections** entity type:

1.  Select **Add entity type** from the ribbon. 

> ![](./media/image38.png)

2.  Enter **Inspections** as the name and select **Add Entity Type**. 

> ![](./media/image39.png)

3.  Switch to the **Bindings** tab → **Add data to entity type**. 

![](./media/image40.png)

4.  Choose your data source, select your **Lakehouse** and
    select **Add**. 

> ![](./media/image41.png)

5.  Select the **inspections** table and select **Next**.

> ![](./media/image42.png)

[TABLE]

6.  Configure a **Static** data binding with the following columns:

- Select **Save**.

![](./media/image43.png)

7.  Select **Add entity type key** → choose **inspection_id**.

![](./media/image44.png)

8.   Select **inspection_id** as the key property and select **Save**.

![](./media/image45.png)

> Summary of Entity Types
>
> ![](./media/image46.png)

# Exercise 3: Create data agent

Ontology (preview) integrates with [Fabric data agent
(preview)](https://learn.microsoft.com/en-us/fabric/data-science/concept-data-agent) to
let you ask questions in natural language, and get answers grounded in
the ontology's definitions and bindings.

## Task 1: Create data agent with ontology (preview) source

Follow these steps to create a new data agent that connects to your
ontology (preview) item.

1.  Now, click on **Fabric IQ OntologyXX** on the left-sided navigation
    pane.

![](./media/image47.png)

2.  In the **Fabric** home page, select **+New item.** In the Filter by
    item type search box, enter +++**data agent**+++ and select the Data
    agent

> ![](./media/image48.png)

3.  Enter **+++** **FabricDataAgent+++** as the Data agent name and
    select **Create**.

> ![](./media/image49.png)

4.  In **FabricDataAgent** page, select **Add a data source**

> ![](./media/image50.png)

5.  In the OneLake catalog tab, select the **NetworkOperationsOntology**
    Ontology and select **Add.**

![](./media/image51.png)

When the agent is ready, it opens.

![](./media/image52.png)

> Which inspector performed the most inspections?

![](./media/image53.png)

![](./media/image54.png)

![](./media/image55.png)

![](./media/image56.png)

![](./media/image57.png)

![](./media/image58.png)

# Exercise 4: Create a Storage account

1.  From the Azure portal Home page (+++<https://portal.azure.com/+++>),
    select **Storage accounts**.

![A screenshot of a computer AI-generated content may be
incorrect.](./media/image59.png)

2.  Select **+ Create** to create a new Storage account.

![A screenshot of a computer AI-generated content may be
incorrect.](./media/image60.png)

3.  Enter the below details, accept the default values in the other
    fields and click on **Review + create**.

    - Subscription – Select your **assigned subscription**

    - Resource group – Select your **assigned Resource
      group** (**ResourceGroup1**)

    - Storage account name –
      +++[**leavepolicystg@lab.LabInstance.Id**](mailto:leavepolicystg@lab.LabInstance.Id)+++

    - Region – Select @lab.CloudResourceGroup(ResourceGroup1).Location

    - Primary service – Select **Azure Blob Storage or Azure Data Lake
      Storage Gen 2**

![A screenshot of a computer AI-generated content may be
incorrect.](./media/image61.png)

4.  Once the validation passes, click on **Create**.

![A screenshot of a computer AI-generated content may be
incorrect.](./media/image62.png)

5.  Once the resource creation succeeds, click on **Go to resource**.

![A screenshot of a computer AI-generated content may be
incorrect.](./media/image63.png)

![A screenshot of a computer AI-generated content may be
incorrect.](./media/image64.png)
