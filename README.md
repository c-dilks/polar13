steps to manipulate polarimetry csv file into something readable

1. copy csv data from polarimetry group
  - old method: http://www.phy.bnl.gov/cnipol/ --> fill results --> 
   table format = csv, save to "polarimetry.csv"
  - new (more correct method): https://wiki.bnl.gov/rhicspin/Results --> Run 12 fill by fill results
   (for run 12 data table... run13 data table not finalised, still using old method)

2. remove "+-" symbols: cat polarimetry.csv | sed 's/+-//g' > polarimetry.dat

3. there is some missing information in some rows.. put zeros here
   (check with the formatted table from the website to make sure you're putting
   zeros in the proper columns)

4. run "mkTree.C" to build "pol.root", which is a tree containing the data from the csv file

5. run "mkPlots.C" to draw some polarimetry plots
