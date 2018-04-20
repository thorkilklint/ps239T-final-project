## Short Description

Give a short, 1-2 paragraph description of your project. Focus on the code, not the theoretical / substantive / academic side of things. 

## Dependencies

List what software your code depends on, as well as version numbers, like so:.

1. R, version 3.4.1

## Files

List all other files contained in the repo, along with a brief description of each one, like so:

### Data

All data files are available as in a csv-format and in an r-data-set-object format. I use the latter in my scripts, as it automatically reads variables in the format I saved them in. The following list just mentions the csv-version:

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

1. 01_Get_and_clean_agenda_data.Rmd: 
2. 02_Get_and_clean_member data.Rmd: 
3. 03_Get_resume_data.Rmd: 
4. 04_Clean_resume_data.Rmd: 
5. 05_Text_analysis_discriminating_words.Rmd:

### Results

1. member_party_and_education.pdf: 
2. which_sessions_are_relevant.pdf: 
3. word_proportion_leftwing_dansk_folkeparti.pdf:
4. word_proportion_government.pdf


## More Information

Include any other details you think your user might need to reproduce your results. You may also include other information such as your contact information, credits, etc.
