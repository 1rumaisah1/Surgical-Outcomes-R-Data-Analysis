# licorgice-gargle-R-Data-Analysis
<br>Data analysis of an open source surgical dataset - Indexing, creating graphs, sorting, etc.</br>
<br>install.packages("medicaldata") -- 19 datasets, for reprodiucible medical research w/ R </br>
<br>library(medicaldata)</br>
<br>library(tidyverse)</br>
<br>library(dplyr)<br>
<br>data(package = "medicaldata") -- this will list out each the of the 19 datasets</br>
<br><b><i> The dataset licorice_gargle is from an RCT of licorcle Gargle before intubation for elective thoracic surgery: Ruetzler et al.<br> “A Randomized, Double-Blind
Comparison of Licorice Versus Sugar-Water Gargle for Prevention of Postoperative Sore
Throat and Postextubation Coughing".</i></b></br>
<br>str(licorice_gargle) <br> To list out the numerical data from the dataset licorice_gargle</br>
<br>LG <- licorice_gargle -- replacing the numerical data table with a variable for convenience</br>
<br>clss(LG) -- to determine and confirm the class of LG</br>
<br>Surgery_size <- LG$intraOp_surgerySize -- to assign a variable for convenience</br>
<br>order(Surgery_size) -- to arrange the numerical data values in chronological order</br>
<br>throat_pain <- licorice_gargle$postOp4hour_throatPain</br>
<br><b>The throat pain is assessed on an 11-point likert scale, 0 = no pain and 10 = worst pain. The maximum pain level<br>
recorded in all patients [n=236]. Now, I will determine the maximum position and pain level, and whether there are any NA values in the pain
levels recorded.</b></br>
<br>which.max(throat_pain)</br>
<br><i>[1] 234</i> -- The maximum recorded pain level is at the index 234. </br>
<br>throat_pain[234]</br>
<br><i>[1] 7</i> -- Therefore the maximum pain level is recorded as 7, at position 234.</br>
