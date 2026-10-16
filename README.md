# licorgice-gargle-R-Data-Analysis-wip
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

<br>class(LG) -- to determine and confirm the class of LG</br>

<br>Surgery_size <- LG$intraOp_surgerySize -- to assign a variable for convenience</br>

<br>order(Surgery_size) -- to arrange the numerical data values in chronological order</br>

<br>throat_pain <- licorice_gargle$postOp4hour_throatPain</br>

<br><b>The throat pain is assessed on an 11-point likert scale, 0 = no pain and 10 = worst pain. The maximum pain level<br>
recorded in all patients [n=236]. Now, I will determine the maximum position and pain level, and whether there are any NA values in the pain
levels recorded.</b></br>

<br>which.max(throat_pain)</br>

<br><i>234</i> -- The maximum recorded pain level is at the index 234. </br>
<br>throat_pain[234]</br>

<br><i>7</i> -- Therefore the maximum pain level is recorded as 7, at position 234.</br>

<br>anyNA(throat_pain)</br>

<br>TRUE</br>

<br>which(is.na(throat_pain), arr.ind = TRUE)</br>

<br><i>113, 123</i> - At positions throat_pain[113,123], there is a value of NA. Therefore, of the 236 patients (n=236), only 234 patients reported post-operative pain on swallowing as per the Likert scale, four hours after extubation.</br>

<br>throat_pain <- table(throat_pain)</br>

<br>hist(throat_pain,<br>
        main = "Pain levels report",<br>
        xlab = "Pain levels",<br>
        ylab = "Patient Population, 4 hours post-extubation",<br>
        col = "skyblue",<br>
        xlim = c(0,10),<br>
        ylim = c(0,234)<br>
        )</br>
<br>
    <img width="499" height="452" alt="62067a9f-2418-467b-80c8-75d57109dd27" src="https://github.com/user-attachments/assets/a6e46692-7084-4da7-b388-456952f8085d" />
</br>
        <br>treatment <- LG$treat - <b> The treatment is recorded as 0 = licorice 0.5g, 1 = sugar 5g.</b></br>
       <br> treatment <- factor(licorice_gargle$treat,<br>
                    levels = c(0,1),<br>
                    labels = c("sugar","licorice")<br>
                    )</br>
<br>table(licorice_gargle$treat)<br>
table(treatment)</br>

        


