# Vanguard A/B Testing EDA Project
by The Cubers Group

- Alejandro Figueroa
- Bryan Frank
- Dylan Sedeno

## Project Overview

You are a newly employed data analyst in the Customer Experience (CX) team at Vanguard, a US-based investment management company. Your first task involves analyzing the results of a digital experiment conducted by the team.

### The Digital Challenge

In the ever-evolving digital world, Vanguard aimed to enhance the user experience for their clients. They hypothesized that a more intuitive and modern User Interface (UI), along with timely in-context prompts (cues, messages, hints, or instructions provided to users directly within the context of their current task or action), could streamline the online process and encourage more clients to complete it.

### The Experiment

The experiment involved modifying the UI and introducing in-context prompts to observe whether these changes would lead to higher completion rates among clients.

## Table of Contents

1. [Introduction](#introduction)
2. [Data Description](#data-description)
3. [Analysis](#analysis)
4. [Results](#results)
5. [Tableau Public Workbook](#tableau-public-workbook)
6. [Google Slides Presentation](#google-slides-presentation)
7. [Trello Board](*trello-board)

## Introduction

In this project, we aim to analyze the impact of UI improvements and in-context prompts on client behavior. The analysis is conducted using various data analytics techniques, with visualizations created in Tableau to present the findings effectively.

## Data Description

The three main datasets used for the project were:
  - Client Profiles (df_final_demo): Contains demographic data on Vanguard clients
  - Digital Footprints (df_final_web_data): Trace of client interactions with Vanguard’s online process. 
  - Experiment Roster (df_final_experiments_clients): List that reveals the clients that were part of the grand experiment.


## Analysis

The data cleaning process was straightforward and comprised of the following tasks:
  - Disregarded clients who did not participate in the experiment by dropping nulls in the client profiles dataframe.
  - Removed outliers for better data visualization and analysis for client balance information.
  - Dropped unnecessary columns, renamed columns, and maintained naming conventions. 
  - Performed merging between:
    - Client Profiles and Digital Footprints on Client ID column (demographic analysis)
    - Experiment Roster and Digital Footprints on Client ID column (KPI analysis)
   
Our target KPI’s were:
  - Completion Rate
  - Bounce Rate: Frequency with which clients failed to progress past the initial step in the online process.
  - Drop Rate: Indicates whether clients forfeited the online process prior to reaching the final confirmation step.

In addition, we wanted to analyze how specific variables affect the drop rate such as:
  - The number of calls made in the last six months 
  - Client tenure
  - Client investment balance
    
Finally, we were interested in the gender wage gap discourse, so we opted to investigate if gender affects the investment balance.


## Results

From testing completion, bounce, and drop rates we see that:
  - The Test group completed the process more than control
  - Test group had the lower bounce rate 
  - And there was was no difference when it came to drop rate

With the Chi squared test we gained the following insights.
  - Test group clients having longer tenure with the company had a noticeable raise in completion 
  - Changes made allowed clients who called support at least once to complete the online process 
  - The two-sample t-test showed that:
  - Male clients have more invested than any other client 
  - And that clients that did not drop have more invested in general


## Tableau Public Workbook

The interactive visualizations created for this analysis can be accessed on Tableau Public. These visualizations provide detailed insights into the experiment's results.

[View the Tableau Public Workbook](https://public.tableau.com/views/Ironhack-EDA-Project/DropClientsbyInvestmentBalance?:language=en-US&publish=yes&:sid=&:display_count=n&:origin=viz_share_link)

## Google Slides Presentation

[View the Google Slides Presentation](https://docs.google.com/presentation/d/1NTZg2U_izvyAM4VOe43xKWZlGpBYQjS60Ru1KHkG1Ic/edit?usp=sharing)

## Trello Board

[View our Trello Kanban board](https://trello.com/invite/b/SkqsBcVP/ATTIa1b54c4c63ebf9afa82c3347aabb234983C0EB9D/the-red-musers)
