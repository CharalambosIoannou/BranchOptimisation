Usage
=====

.. _dashboard:

Dashboard
------------

.. note::

   This page is under development.
   

Map
**********

Also called `First View` contains information about diffent Bank of Cyprus branches along with their competitors.
On the top a map which can show various bank branches (BoC and competitors) with different filters is displayed. These filters are:

1) Show Bank of Cyprus branches per city on the map
2) Show Competitor bank branches on the map
3) Show the driving distance from each branch (**pending**)


A screenshot of the map with the filters can be seen below:

.. image:: images/dashboard1.PNG
  :width: 700
  :alt: First View
  
  
Branch Information
**********


Scrolling down in the dashboard reveals aggregated information about Bank of Cyprus branches. There is a header in which the aggregation can be changed. 

Information can be displayed as `Cyprus` which aggregate information about **all** Bank of Cyprus branches or can select each city individually which is going to aggregate information of the branches for the **city** selected. 

The information which is displayed is:

1) The branch types each city has. If specific branch is selected then this shows the branch type of the selected branch
2) The number of employees
3) The digital engagement of the customers.


The screenshots can be found below:

* Selecting **all** branches:

.. image:: images/dashboard2.PNG
  :width: 700
  :alt: First View
  
.. image:: images/dashboard4.PNG
  :width: 700
  :alt: First View

* Selecting a specific city (**Nicosia**):

.. image:: images/dashboard3.PNG
  :width: 700
  :alt: First View

* Selecting a specific branch in a city (**city: Nicosia, branch: 117**):

.. image:: images/dashboard5.PNG
  :width: 700
  :alt: First View




Closing Branch
----------------

This is the main tab when a new branch is needed to be closed.

The user first has to select either of the two options:

* **Supervised:** Select this option if the number of branches to close is known.
* **Unsupervised:** Select this option if the number of branches to close is unknown. This means the algorithm will suggest the optimal branches to close.

A screenshot of these options is shown below:

.. image:: images/closing_branch1.PNG
  :width: 700
  :alt: First View


After selecting an option, more inputs are required for the algorithm to run. These inputs are:

1) In which city do you wish to close branches?
2) How many branches do you wish to close? (If **supervised** option selected only)
3) Branches from which segments should be forbidden from closing?
4) The model forms geoclusters with branches that are within a certain distance between them. In order to ensure geographical coverage the model never proposes to close all branches in the same geocluster. What should be the maximum distance between the branches of the geoclusters? 

5)   
  * The model considers the location of any competitive branches prior to suggesting branches to close. Would you like the presence of any competitor bank close to a BoC branch to forbid the model from closing the specific branch? 
  * If you made a selection in question 5a, how far from the BoC branch should the competitor branch be located to be considered as a restriction to closing?
  
6) Should the model be allowed to close rural branches?
7)  What is the revenue loss (as a % of the total branch revenue) that you expect to have when closing a branch?
8)  Please indicate the maximum number of clients that each banker type may have registered on them (FYI the original direction from Hays was: CSRO: 4500, RRO: 1000, PRO: 800, SBRO: 300).
9) Please indicate the weight of individual customers should have on the capacity of a banker, according to their digital engagement score?






Customer Migration
----------------

test


Update Data
----------------

test
