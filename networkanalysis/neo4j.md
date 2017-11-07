# Notes on using the Panama Papers database with neo4j

# ICIJ Panama Papers Data

The ICIJ share data from the Panama Papers [on their page here](https://offshoreleaks.icij.org/pages/database). The data can be downloaded in two forms: 

* as a collection of large CSV files
* as a collection of neo4j databases

It is useful to download both. 

You are recommended to use BitTorrent. This is very simple to use: firstly download BitTorrent from the link on the page; secondly, download the BitTorrent link to the database. This is just a link, not the database itself. Once downloaded, double-click on it and it will open BitTorrent to download the database itself - just confirm this and wait for it to download.

## Understanding the data

The CSV files are useful because they allow you to see the structure of the data before you begin using neo4j. These are very large CSV files, so you may find it easier to import them into RStudio if you are comfortable importing CSV files. 


## Using the database files - getting neo4j started

Once you download the database files, the folder includes a README file which contains this text copied below:

--------------------------------------
This distribution contains the following:

 - Panama Papers data, packaged as native Neo4j database files
 - Neo4j 3.0.1, to serve the data
 - a custom launcher to run Neo4j with the right configuration

Get Started
-----------

Launch our customized distribution of Neo4j:

0. Optionally, check that the software hasn't been tampered with, verify the
  SHA  hash of the panama-papers-mac.tgz file against the value posted
  on our website.
  - for mac, see http://www.cnet.com/news/how-to-quickly-check-a-files-checksum-in-os-x/ 
1. Right-click on launch_neo4j.command and then "Open With" and then choose Terminal.app
2. Depending on your system settings, you may get a security warning about
   an "unidentified developer." Click "OK" to proceed.
3. Start the database by clicking the "Start" button

First steps with Neo4j:

1. Click the URL which appears in the green box to load the Neo4j user interface
2. In your web browser, you'll see the Neo4j Browser, a client application for
   accessing the database
3. Since you're running for the first time, you'll need to set a new password
   - start by entering the default username/password of `neo4j/neo4j
   - enter a new password
4. Now you're ready to explore the Panama Papers data

## Using neo4j

Once it is running neo4j will work in your browser at http://localhost:7474/browser/ - this is not a website, but your own computer. You do not need to be connected to the internet.

The neo4j outlined in the instructions above is:

> “a distribution of Neo4j available with the data in it. This will allow you to query the database to fully explore from your computer the connections between people and companies. The package also includes a guide that explains how to use Neo4j.”

This is very helpful, as it means you do not need to connect to the data, and you can follow — and adapt — some example queries from the guides.

Once running, you should have an empty box with a `$` sign - this is the *command line*. And taking up most of the page, a splash screen introducing the data. Notice that just above it is the command:

`:play https://cloudfront-files-1.publicintegrity.org/offshoreleaks/neo4j/guide/index.html`

If you click on the link to ‘Shape of the data’ underneath, this loads the following command:

`:play https://cloudfront-files-1.publicintegrity.org/offshoreleaks/neo4j/guide/datashape.html`

Click on the ‘run’ arrow next to that command line (or press CTRL+ENTER) to run that command and load the page.

Likewise, if you click ‘Investigative Queries’ it will load this:

`:play https://cloudfront-files-1.publicintegrity.org/offshoreleaks/neo4j/guide/examples.html`

It is worth looking at both, so you get an idea of the data and queries that can be run, while clicking the arrows at the edge of the screen to move to subsequent pages.

Most queries in the examples can be clicked on, which will bring them into the command line above. Again, click on the ‘run’ arrow next to that command line (or press CTRL+ENTER) to run that command and see the results of the query. You can also ‘star’ a query to save it to your favourites (these are accessible by clicking the star icon on the left side)

When a query is run, look to the left of the results. Normally there will be 3 or 4 different ways of looking at it:

* **Graph**: This shows a network graph of the connections you’ve asked to see. It is only available if your query relates to connections
* **Rows**: This shows a table of the results, if applicable
* **Text**: This also shows a table, but this time it uses pure text characters, like the pipe symbol, to draw it
* **Code**: This is a description, in code, of the query you have made and the responses that it generated. It’s unlikely you’ll use this.

Above the results are buttons that allow you to: 

* Download the results of the query (as JSON or CSV if a table; as PNG or SVG too if a network graph)
* Pin the results to the top (every time you run a new query it would otherwise be pushed down)
* Expand the results to full screen
* Close the results

If you have a network graph, you can double-click on any node to expand the connections from that node.


