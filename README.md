# ps239t-final-project
PS 239T Final Project - Jennie Barker - May 10, 2020 

## Short Description

I used my PS239T project as an opportunity to explore existing datasets on my topic of interest, which is why recipient countries choose to welcome or restrict democracy assistance. While no datasets focus directly on this topic, there are a few datasets that look at restrictions of foreign funding to NGOs. This is helpful because while democracy assistance can go to governments, it often goes to NGOs within civil society. 

Given topic and availability constraints, my main dataset of interest is “State Restrictions on of Civil Society” from Kristin Bakke et al. (2020), which, in contrast to some of the other existing datasets, has disaggregated data from 1994-2014 on the various restrictions that states have placed on civil society, including most importantly international funding to NGOs. This dataset explicitly focuses on human rights NGOs and both informal and formal restrictions. 

I compared Bakke et al (2020) with data from Kendra Dupuy et al. (2016), which features data on formalized legal restrictions on foreign funding to NGOs. I also merged a subsetted dataframe from Bakke et al (2020) with data from Inken von Borzyskowski (2018), V-DEM, and Gallup Analytics to examine the relationship between international funding restrictions and requests for election assistance, civil society participation, and public opinion of the U.S. and China, respectively. 

It is important to note that I mainly focused on analyzing and visualizing descriptive statistics of the data with tidyverse, ggplot2, and rworldmap packages. 


## Dependencies

R, 3.6.2

## Files
Code/
01_InitialDataset_CleaningViz.Rmd: In this script file, I download, clean, and analyze the initial dataset of interest, which is:	Kristin Bakke, Neil Mitchell and Hannah Smidt, Replication data for “[State Restrictions of Civil Society](https://kristinbakke.com/state-restrictions-of-civil-society/),” 2020. I analyzed the variables: international funding restrictions, visa difficulties and denials, cooptation, arrests, and harassment. 
02_InitialDataset_Comparison.Rmd: In this script file, I download data from Kendra Dupuy, James Ron, and Aseem Prakash, "[Hands Off My Regime!](https://jamesron.com/scholarly/)" 2016. I compare this data with Bakke et al. (2020) and create a map using rworldmap. 
03_OtherVariablesViz.Rmd: In this script file, 1.) I download data from Inken von Borzyskowski, Replication Data for “[Resisting Democracy Assistance: Who Seeks and Who Receives Election Assistance](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/IDAFGF),” 2018 to analyze and visualize the relationship between international funding restrictions and requests for election assistance. 2.) I download data from [V-dem](https://www.v-dem.net/en/) to analyze and visualize the relationship between international funding restrictions and civil society participation. And 3.) I download data from [Gallup Analytics](https://www.gallup.com/analytics/213617/gallup-analytics.aspx) on worldwide public opinion to analyze and visualize the relationship between international funding restrictions and public opinion on the U.S. and China. 

Data/
1-Bakke_restrictions_raw.csv: Raw data from Bakke et al. (2020). 
2-Bakke_restrictions_new.csv: Subsetted data from Bakke et al. (2020) that removed observations from donor countries and selected only a few variables, such as international funding restrictions. 
3-Bakke_restrictions_new_edited.csv: Subsetted data from Bakke et al. (2020) that mutated arrests and harassment variables from categorical to binary. 
4-Dupuy_handsoff_raw.csv: Raw data from Dupuy et al. (2016).
5-Dupuy_handsoff_new.csv: Subsetted data from Dupuy et al. (2016) that removed observations from donor countries. 
6-Map.csv: Data from Bakke et al. (2020) and Dupuy et al. (2016) used to create rworldmap visualization. 
7-Borzyskowski_assistance_raw.csv: Raw data from Borzyskowski (2018). 
8-Borzyskowski_assistance_new.csv: Subsetted data from Borzyskowski (2018) to match observations in Bakke et al. (2020)
9-Borzyskowski_Bakke.csv: Merged dataset created from Borzyskowski (2018) and Bakke et al. (2020). 
10-Vdem_subsetted.csv: Subsetted data from V-Dem to remove donor countries and year observations outside of 1994-2014 (the years of observation in Bakke et al. 2020). 
11-Vdem-subsetted_new.csv: Subsetted data from V-Dem to match exactly Bakke et al. (2020) observations. 
12-Bakke_Vdem_subsetted.csv: Merged dataset from Bakke et al. (2020) and V-Dem. 
13-Gallup_US_subsetted.csv: Subsetted data from Gallup Analytics on public approval and disproval of U.S. leadership. 
14-Gallup_China_subsetted.csv: Subsetted data from Gallup Analytics on public approval and disproval of Chinese leadership. 

Results/
1-initialdataset_intlfunding_lineplot.png: Initial line plot of total number of new international funding restrictions over time (1994-2014) (from Bakke et al. (2020))
2-initialdataset_intlfunding_barplot_years.png: Initial bar plot of total number of new international funding restrictions by year (from Bakke et al. (2020))
3-initialdataset_intlfunding_barplot_countries.png: Initial bar plot of total number of new international funding restrictions by country (from Bakke et al. (2020))
4-initialdataset_intlfunding_visas_cooptation.png: Initial line plot comparing countries with new international funding restrictions, visa difficulties, and cooptation of NGOs over time (1994-2014) (from Bakke et al. (2020))
5-initialdataset_intlfunding_harassment.png: Initial bubble plot comparing countries with new international funding restrictions and systematic harassment of NGOs (1994-2014) (from Bakke et al. (2020))
6-restrictions_map.png: rworldmap with countries identified with restrictions in Bakke et al. (2020), in Dupuy et al. (2016), and in datasets. 
7-funding_electionassistance.png: bar plot showing requests for election assistance among subset of countries with restrictions (from Bakke et al. 2020 and von Borzyskowski 2018)
8-funding_electionobservers.png: bar plot showing requests for election observers among subset of countries with restrictions (from Bakke et al. 2020 and von Borzyskowski 2018)
9-funding_civilsociety.png: bar plot showing aggregated mean civil society participation index value among country-year observations with restrictions and those without restrictions (from Bakke et al. 2020 and V-Dem)
10-funding_civilsociety_byyear.png: bar plot showing aggregated mean civil society participation index value among country-year observations with restrictions and those without restrictions by year (1994-2014) (from Bakke et al. 2020 and V-Dem)
11-funding_civilsociety_coefficients.png: plot showing coefficients from binomial logit regression of international funding restrictions and civil society participation index (from Bakke et al. 2020 and V-Dem)
12-funding_usapproval_total.png: aggregate mean approval of U.S. leadership among countries with restrictions and countries without restrictions (from Bakke et al. 2020 and Gallup Analytics Worldwide Polls) 
13-funding_usapproval_year.png: aggregate mean approval of U.S. leadership among countries with restrictions and countries without restrictions by year (2009-2014) (from Bakke et al. 2020 and Gallup Analytics Worldwide Polls) 
14-funding_chinasapproval_total.png: aggregate mean approval of Chinese leadership among countries with restrictions and countries without restrictions (from Bakke et al. 2020 and Gallup Analytics Worldwide Polls) 
15-funding_chinasapproval_year.png: aggregate mean approval of U.S. leadership among countries with restrictions and countries without restrictions by year (2009-2014) (from Bakke et al. 2020 and Gallup Analytics Worldwide Polls) 
16-funding_usdisapproval_year.png: aggregate mean disapproval of U.S. leadership among countries with restrictions and countries without restrictions by year (2009-2014) (from Bakke et al. 2020 and Gallup Analytics Worldwide Polls)
17-funding_chinadisapproval_year.png: aggregate mean disapproval of Chinese leadership among countries with restrictions and countries without restrictions by year (2009-2014) (from Bakke et al. 2020 and Gallup Analytics Worldwide Polls)
18-funding_NGOtrust.png: aggregate mean trust of NGOs and charitable organizations among countries with restrictions and countries without restrictions (from Bakke et al. 2020 and Gallup Analytics Worldwide Polls)
19-funding_NGOtrust_bycountry.png: aggregate mean trust of NGOs and charitable organizations among countries with restrictions and countries without restrictions by year (2009-2014) (from Bakke et al. 2020 and Gallup Analytics Worldwide Polls)

More Information
Please contact Jennie Barker at jlbarker@berkeley.edu if you have any questions or comments about the data discussed above. 
