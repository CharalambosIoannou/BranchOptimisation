Update Data
=====

.. _update:



This is the main tab when new data are needed to be used by the application. 


Inputs
------------
**The application takes 5 CSV files as inputs**. These are:

1) ``competitor_branches.csv`` -> This file has branch information of all banks in Cyprus. This includes Bank of Cyprus branches and Competitor branches.
2) ``iso_branches_competitor_district_distances.csv`` -> This file has information regarding the distances of each Bank of Cyprus branch with its Competitor branches.
3) ``iso_branches_boc_distances.csv`` -> This file has information regarding the distances of each Bank of Cyprus branch with the other Bank of Cyprus branches.
4) ``hays.csv`` -> This file has information regarding the Hays.
5) ``parking.csv`` -> This file has information regarding each branch specifications such as parking spaces and square meters.


Explanation
------------

* The ``competitor_branches.csv`` is updated manually.
* The ``iso_branches_competitor_district_distances.csv`` and ``iso_branches_boc_distances.csv`` is obtained from the SQL server (Branch_Optimisation database) **after** running a Python script.
* The ``hays.csv`` and ``parking.csv`` is obtained from the bank



Step-by-Step Guide 
------------

To update the data first have a laptop with **Python** installed and follow these steps:

1) Update ``competitor_branches.csv``. Manually add or remove BoC and Competitor branches that are currently in operation
2) Drop ``dbo.new_iso_branches`` table
3) Insert ``competitor_branches.csv`` as`dbo.new_iso_branches` table
4) Run ``python api_script.py``
5) Run ``python api_script_boc_only.py``
6) Select latest data:

.. code-block:: sql

   SELECT  [branch_id]
      ,[competitor_branch_id]
      ,[distance_m]
      ,[distance_min]
      ,[geo_distance_m]
      ,[created_at]
   FROM [Branch_Optimisation].[dbo].[iso_branches_competitor_district_distances]
   WHERE cast (created_at as date) = '2022-07-11' -- add new Date
   
   
Export result as ``iso_branches_competitor_district_distances.csv`` file

7) Select latest data:

.. code-block:: sql

  SELECT  [branch_id1]
      ,[branch_id2]
      ,[district]
      ,[distance_m]
      ,[distance_min]
      ,[geo_distance_m]
      ,[longitude1]
      ,[latitude1]
      ,[longitude2]
      ,[latitude2]
      ,[created_at]
  FROM [Branch_Optimisation].[dbo].[iso_branches_boc_district_distances]
  WHERE cast (created_at as date) = '2022-07-11' -- add new Date
  
Export result as ``iso_branches_boc_distances.csv`` file.



8) Send the following files to BoC laptop:
    * competitor_branches.csv
    * iso_branches_boc_distances.csv
    * iso_branches_competitor_district_distances.csv
9) Run Shiny and go to update Tab. 
10) Upload CSV files and press Update button. See the screenshot below:


.. image:: images/update_data.PNG
  :width: 700
  :alt: First View
  
