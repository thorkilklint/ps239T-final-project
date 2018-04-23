## Short Description

The code in this project follows four steps, in order to analyse wether the way Danish Parliament members address the issue of immigration differs across different member parties, with the opportunity to answer the same question for other member traits. *First*, I have written an R-script that scrapes the agendas for different parliament settings, counting the number of times the Minister of Immigration occurs on the agenda, thereby enabling me to pick relevant debates. *Second*, I use the Danish Parliament API to get data on the party and education of each parliament member. *Third* I scrape the transcripts, what I call the resumes, of relevant party debates, and *finally* I apply discriminative, unsupervised text analysis to answer my research question. 

## Dependencies

My code depends solely on R, version 3.4.1. Packages to supply Base-R are installed in the code. 

## Files

My project contains the following files

### Data

I have made all data files  available in a csv-format *and* in an r-data-set-object format. I use the latter in my scripts, as it automatically reads variables in the format I saved them in, but I know, that not everyone uses R. The following list just mentions the csv-versions of every file:

1. url_agenda_df.csv: dataset scraped from the Danish parliment website. Includes information on all Parliament sessions of the term 2017-2018 and the number of mentions of the minister of immigration.
2. all_members_data_raw.csv: raw dataset on 292 Danish Parliament members collected via the Danish Parliament API.
3. all_members_data.csv: cleaned dataset on 292 Danish Parliament members. Contains the following variables:
    - *id*: Id number of the member
    - *name*: Name of the member
    - *typeid*: the type-id of the member, parliament members have typeid=5
    - *biografi*: An html-text, in character format, containing each members biografi
    - *party*: The members party
    - *education*: The members education
    - *academic*: A logical vector indicating if the member has an academic education
    - *education_fill*: A character version of academic for plotting
4. url_resume_df.csv: a dataframe with a url for every transcript/resume of Danish parliament debates from 2016-2018
5. resume_urls_to_loop_over.csv: a subset of the dataset above, only containing urls for the the relevant parliament sessions, where the Minister of Immigration was on the agenda more than 2 times. 
6. resume_debate_1.csv : A raw dataset, consisting of the debate resumes scraped from the Danish Parliament website. A dataset exist for each of the investigated debates, 1-11
7. immigration_debate_text_data.csv: the main dataset of the project. This data combines text data for all relevant statements made in all of the investigated debates. The data is on statement level. Contains the following variables:
    - *time*: when was the statement made
    - *name*: name of the member who made the statement
    - *chairman*: was the statement made by the chair of the session
    - *id*: the id of the member who made the statement
    - *party*: the party of the member who made the statement
    - *academic*: A logical vector indicating if the member who made the statement has an academic education
    - *education_fill*: A character version of academic for plotting
    - *text*: the statement as a character vector
    - *agenda*: shows which statements move the debate on to a new agenda item
     - *statement_number*: An integer, showing which number the statement had in its original debate

### Code

1. 01_Get_and_clean_agenda_data.Rmd: Collects and analyses agenda data.
2. 02_Get_and_clean_member data.Rmd: Collects and cleans member data from the API
3. 03_Get_resume_data.Rmd: Collects the text resumes from the Parliament website
4. 04_Clean_resume_data.Rmd: Cleans the text resumes from the Parliament website, e.g. by merging it with the member data
5. 05_Text_analysis_discriminating_words.Rmd: Analyses and visualizes how use of words differ across party lines. 

### Results

1. member_education_and_party.jpg: A plot showing how party member education - academic or not - differ between the parties in the Danish Parliament.
2. which_sessions_are_relevant.jpg: A plot showing the amount of times the Minister of Immigration appears on a Parliament session agenda
3. word_proportion_leftwing_dansk_folkeparti.jpg: Shows the difference between proportions of words between the leftwing parties and the right wing party Dansk Folkeparti
4. word_proportion_government.jpg: Shows the difference between proportions of words between the leftwing parties and the Danish Government parties


## More Information

Some of the scraper functions has been set to eval=F, as they may be outdated at one point. A knitted version of each of the coding files is available in the code-folder. 


