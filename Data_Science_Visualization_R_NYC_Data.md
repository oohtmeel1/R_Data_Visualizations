Step 1:
First the data is downloaded. And in order to do that the link in this case is set to be url_in and file_name. 

About the data:
"List of every shooting incident that occurred in NYC going back to 2006 through the end of the previous calendar year."
From catalog.data.gov

``` {r get NYPD data}
url_in <-"https://data.cityofnewyork.us/api/views/833y-fsy8/rows.csv?accessType=DOWNLOAD"
file_name <-("https://data.cityofnewyork.us/api/views/833y-fsy8/rows.csv?accessType=DOWNLOAD")
urls <- str_c(url_in,file_name)
cases <- read_csv(file_name)
```

Step 2
Maybe a good one would be the burough vs the time of occurence, let's see if there is a pattern there selecting just the data we would like to see

```{r make data look nice}
burough2 <- cases %>% 
     select(BORO, OCCUR_TIME, OCCUR_DATE) %>%
    filter(!is.na(OCCUR_TIME))
              
```
Step 3: Data Visualization

Now that the data looks somewhat more presentable
```{r data visualization}
burough2 <- cases %>% 
     select(BORO, OCCUR_TIME, OCCUR_DATE) %>%
    filter(!is.na(OCCUR_TIME))
              
```

So far the data looks meh so I need to further refine it.

