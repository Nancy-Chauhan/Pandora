# Pandora

Collection of random projects. 

### Problem 1 

Problem Statement: Build a simple KV (key-value) store web service with a subscription feature. As a user, I should be able to perform set(key, val) and get(key) operations over HTTP and also subscribe to changes happening to any of the keys.

Deliverables:

1.Server-side implementation of the web service in the language of your choice
2.A CLI client which consumes the web service supporting following commands
a.get <key>: displays the value of an existing key
b.put <key> <value>: sets the value of the given key
c.watch: when executed this displays any new changes happening on the KV store in realtime
3.The code should be committed to a repo on Github
4.The repo should contain a README describing at least how to set up and run the project.6.Using the tools of your choice (ansible, chef, docker, etc), write the deployment configuration for your application
5.The code should be readable and organized. If there are multiple files and directories consider describing them in the README


### Problem 2 

John has a certain kind of amnesia. Every hour, he forgets his name. He’s tired of setting an alarm on his very old phone which doesn’t allow setting cron alarm jobs.
He wants to hire you to create an application which will send him an SMS every hour to remind him of his name. He also wants you to make sure that he doesn’t get alarms during the night when he is asleep.
Since you don’t know which part of the world John lives in, you have to use an SMS provider which can send an SMS to nearly every country. Twilio is a nice service for sending out SMSes. However, sometimes Twilio’s SMS fails, in which case you have to send it again.
Please do the following:
Create a (basic) web based application where John can set his phone number
2. Send an SMS every one hour except at night
3. Try resending an SMS if it fails, but retry no more than 5 times. (There is only so much you can do!)
4. The web application should also log all the failed messages and tell John for how many hours the application has been running.

### Problem 3 

Growing up, our founders counted &quot;Gossip Girl&quot; among their all time favourite TV shows. As a tribute to the show we have decided to build a Gossip Girl service internally. The service tracks changes made in a database and notifies subscribers in real-time to changes they are interested in. For instance, Blair only wants to track changes made to Chuck&#39;s whereabouts while Georgina wants to track everything about everyone. Unfortunately, our developers are busy working on a deus ex machina and since shutting themselves in a room a few weeks ago, have refused to come out. We can&#39;t wait for them any longer and this is where you come in. We&#39;d like you to design and build a notification
system that will allow a HTTP client to subscribe to changes in a MongoDB database in real-time.
With so many of our developers currently unavailable and the last signs of life from that room being sounds of laughter tainted with madness, we are also looking to hire! To increase your chances and to show off your mad skills also allow notifications to be subscribed to at the field level.
To summarize your task
1. Build a notification system to notify subscribers of changes made in a mongodb database
in real-time
2. (For brownie points) Allow subscriptions at the field level of a document.
If, you are not familiar with MongoDB replace MongoDB with a DB of your choice.


### Problem 4 

HLN fetches tweets (leads) from Twitter Streaming API and stores them in Elasticsearch index after text processing and makes searchable and analyzable through a frontend application.

Features
Search query results get their relevance scores boosted for query terms matching in extracted mentions
Search Functionality supports filtering search results on basis of entities (@mentions) and categories (#hashtags)
Displaying simple data analytics with use of Elasticsearch aggregations
MysqlDb based login system

### Problem 5 

https://github.com/khatryshikha/SocialCops-Django 


### Problem 6 

You need to create a REST service that can fetch bank details, using the data given in the API’s query parameters. 

You can use the data available in this repository in your backend db. Write your service in any language of your choice. Host it in Heroku - you can signup for a free account in Heroku. E.g. Here are steps on how you can get a django app running in Heroku in a few minutes. Please use PostgreSQL as your backend DB. You may not be able to load the entire dataset in the free tier - you can make do with 10000 rows.

Essentials your applications should have: 
use PostgreSQL as a backend database
2 GET API to fetch a bank details, given branch IFSC code
3 GET API to fetch all details of branches, given bank name and a city. This API should also support limit and offset parameters
4 APIs should be authenticated using a JWT key, with validity = 5 days

Deliverables: 
Hosting URL 
2 Github repo link to your solution
3 [ IMPORTANT ] Please include a curl script that makes a call to each of the above mentioned APIs(which includes the JWT key) in your repo while demonstrating the limit and offset parameters
4 Time taken to complete this exercise

### Problem 7 

https://bitbucket.org/spotmentordev/backend-assessment/src/master/

### Problem 8 

Managing campaigns using Rule Based Engine
 
Tyroo needs to effectively manage Swiggy's budget for advertisement on Social platforms like Facebook and Snapchat. Industry experts at Tyroo has seen that when following conditions are met on the day, it is best to pause the campaign and then start again on the next day to reduce spilling of budget.
 
Whenever any one of the following condition is met, campaign is paused and user is notified.
 
        `eCPM` >= $5.00 AND `Impressions` >= 1000000
        `Spend` >= $1000.00 AND `eCPC` <=  $0.20
        `Clicks` >= 50000 AND `Installs` <= 100
        `eCPI` >= $2.00 AND `Installs` >= 100
 
Variables/Metrics:-
    Impressions - how many times an as had been viewed
    Clicks - how many times an ad has been clicked
    Installs - how many times people have installed Swiggy's app through Tyroo's ad on Snapchat/Facebook
    Spend - how many dollars have Swiggy spent on ads for today
    eCPM - Cost per mile impressions (Spend * 1000 / Impressions)
    eCPC - Cost per click (Spend / Clicks)
    eCPI - Cost per install (Spend / Installs)
 
Actions:-
    Notify
    Pause campaign
    Start campaign
 
We want you to create a rule based engine that enables campaign managers to setup these rules through a user interface and receive notification through email.
 
For frontend, create a single page web app with following features:-
1) Login screen with email and password
2) On successful login, user should be redirected to a page having an "Add Rule" button which allows user to create a new rule through a modal (like a contact form). The Create Rule modal must have following things:-
    a) Rule name
    b) Campaigns - to which campaign, should the rule be attached (multiselect field)
    c) Schedule - at what time should this rule be triggered
    d) Conditions - text box in which rules can be specfied as an IF..ELSE condition (`eCPM` >= $5.00 AND `Impressions` >= 1000000)
    e) Action - actions that needs to be taken
    f) Status - Activated/Deactivated
3) The same page should have a table of all the rules that has been created by the user. Each rule line in the table should specify Rule name, Campaigns, Rule Schedule, Rule Status (Activated/Deactivated) and an edit button. The edit button opens the same Create Rule modal but with data filled according to the specific rule.
 
For backend, following components are needed:-
1) Rule executor service
    a) The service should run every 15 minutes
    b) It should check for rules that must be executed according to schedule
    c) If the rule should be executed, make a lookup for data and execute the condition in the rule and trigger congiured action if needed.
2) Action executor service
    a) Implement Notify action only
 
You need to create a schema for storing user info, variables/metrics, rules and actions so that your engine is easily extensible if new metrics and actions are introduced. For executing rules, please use the following schema which stores metric data on per minute basis:-
 
    Campaign        Metric              Value           Datetime
    Swiggy             Impressions         5             2019-01-01 10:01:00
    Swiggy             Clicks                   0             2019-01-01 10:01:00
    Swiggy             Installs                 0             2019-01-01 10:01:00
    Swiggy             Spend             0.05             2019-01-01 10:01:00
    Swiggy             Impressions         7             2019-01-01 10:02:00
    Swiggy             Clicks                   2             2019-01-01 10:02:00
    Swiggy             Installs                 1             2019-01-01 10:02:00
    Swiggy             Spend             0.07            2019-01-01 10:02:00
    Netflix               Impressions       84          2019-01-01 10:02:00
    Netflix               Clicks                   6           2019-01-01 10:02:00
    Netflix               Installs                 2           2019-01-01 10:02:00
    Netflix               Spend             1.68        2019-01-01 10:02:00
 
The engine must take little to no time in executing a rule so please design a smart solution which minimzes lookup to the metrics data.
 
Assumptions:-
    1) Pre-configure for only one user Admin, with email as your personal email and random password
    2) A rule can be scheduled as - Every 15 minutes, Every hour, Every day at 12:00 AM
    3) The only action available is 'Notify'
    4) Use dummy names for campaigns. Assume 5 campaigns are there in the system.
    4) Value column represents daily metric value.
    5) Fill the metrics data with random values. Create data for atleast one hour for all campaigns. Data need not be present for every minute in the hour. 
    
### Problem 9 
    
Write a server which can generate and assign random tokens within a pool and release them after some time. Following endpoints should work on your server:

1. Endpoint to generate unique token in the pool.

2. Endpoint to assign unique token. On hitting this endpoint, server should assign
available random token from the pool and should not serve the same token again
until it’s freed or unblocked. If no free token is available in pool, it should serve
404.

3. Endpoint to unblock the token in the pool. Unblocked token can then be served in
(2)

4. Endpoint to delete the token in the pool. Deleted token should be removed from
the pool.

5. Endpoint to keep the tokens alive. All tokens should receive this endpoint within 5
minutes. If a token doesn’t receive a keep-alive in last 5 mins, it should be
deleted from pool and should not be served again.

6. By default each token will be freed/released automatically after 60s of use. To
keep the token allocated to himself, client should request keep-alive (5) on same
token within 60s.

Enforcement: No operation should result in iteration of whole set of tokens; i.e,
complexity cannot be O(n).

### Problem 10

You are to build a simple program called TapSearch that achieves these objectives.

It takes in multiple paragraphs of text, assigns a unique ID To each paragraph and stores the words to paragraph mappings on an inverted index. This is similar to what elasticsearch does. This paragraph can also be referred to as a ‘document’

Given a word to search for, it lists out the top 10 paragraphs in which the word is present



Few points to consider

Tokenize to words by splitting at whitespace

Convert all words to lowercase

Index these words against the documents they are from

Generate a unique ID for every document that is index

A paragraph is defined by two newline characters



TapSearch APIs you’ll need to  build

clear - Clear the index and all indexed documents

index - Index a given document (After having split the input into paragraphs a.k.a document )

Search - Given a word, search for it and retrieve the top 10 paragraphs (Documents) that contain it



If you successfully create an Inverted Index, Your code will be judged primarily on:

Performance: What we love about Elasticsearch is it’s speed while search for words through an inverted index.

Coding style - How good are your abstraction and overall architecture. Is your code readable and maintainable? We at TapChief strongly believe that well-written code requires little to no documentation.

Your code must be hosted on the cloud, please ONLY use Heroku that is available free of cost. It must have a basic frontend that lets us input text and submit it to be indexed, and another that simple piece of UI that lets us search for top 10 documents given a word.



What exactly you have to put in for your submission.

Link to Cloud deployment

Link to the Github Repo

A Readme file in the repo that briefly explains how to use TapSearch

Your grand Vision. Where would you take this project if you had a tech arsenal at your disposal?

Sample Inputs and Outputs that you have personally tested the program on



If you think this isn’t challenging enough for you, here are two bonus questions to really let you stick out among your peers.



Bonus 1

Add the functionality to upload PDFs and index them. The uploaded PDFs are first parsed into text and then indexed as a document. Given a word to search, return the top 10 matches with the ability to download the PDF



Bonus 2

Add the functionality to upload Images and index them after feature extraction. Given an image to search for, your program must return the top 10 images that look similar to the image I searched for - very similar to Google search by Image.



A few general notes

Your code must be hosted on the cloud

You will provide instruction to accurately test your app in the Readme

You may use whatever language you want to. Only performance and accuracy matters.

Sample Input:

Two documents (paragraphs) separated by two new lines (\n\n)

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Magna ac placerat vestibulum lectus. Elit duis tristique sollicitudin nibh sit amet commodo. Senectus et netus et malesuada fames. Fermentum iaculis eu non diam phasellus vestibulum lorem sed. Dictumst quisque sagittis purus sit amet volutpat consequat mauris. Aliquam ut porttitor leo a diam sollicitudin tempor. Consectetur a erat nam at lectus urna duis convallis. Sed viverra ipsum nunc aliquet bibendum enim facilisis gravida neque. 



Maecenas volutpat blandit aliquam etiam erat velit scelerisque. Lectus sit amet est placerat in egestas erat imperdiet. Ante in nibh mauris cursus mattis. Tellus rutrum tellus pellentesque eu tincidunt. Euismod quis viverra nibh cras pulvinar mattis. Proin nibh nisl condimentum id venenatis a. Quam elementum pulvinar etiam non quam. Arcu dictum varius duis at consectetur lorem donec. Aliquet porttitor lacus luctus accumsan tortor. Duis ut diam quam nulla porttitor massa id.

Sample search

Input - lorem

Results: Paragraph 1 and 2 are returned

Input - Maecenas

        Results: Paragraph 1



Please Note

A preprocessing function is called before the Index function that splits the user submission to index at paragraphs and index each paragraph as a separate document.

### Problem 11

Tales Of A Fourth Grade

Company wants to offer an elementary school system comprehensive student management system as a service

    Users: faculty, staff and student parents
    Requirements:
        track absences, tardies and excuses (entered by parents, faculty or staff)
        generate reports on student activities
        be accessible from the playground
        track student grades and assignments (completed and due)
        parent-teacher forums
        run as an SaaS system from a hosting center
    Additional Context:
        company plans to undertake an aggressive national sales campaign
        current competitor damaged by data breach
        new CIO
        main marketing pitch is around is flexibility, configurability, and (recently added) security
