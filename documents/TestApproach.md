# Test Strategy 

## Introduction
This document explains how the website buggy.justtestit.org was tested. The test includes two parts, API level testing, and UI testing. API level testing was automated as the critical functionalities were executed via API calls. This test practice followed guidelines of the ISTQB test standard.

## Test Planning and Risk Analysis
Website buggy.justtestit.org was analysed and these features were found:
* Frontend displays data returned from API
* APIs are hosted on AWS
* Each functionality has their dedicated API endpoints
* Calculations, e.g. sorting function, are done on API level
* Code/technology complexity is low - simply storing votes from users and display count
* Frontend sometimes needs to display large data, e.g. huge number of comments

Thus, these risks were identified
* API should need to return correct values with correct orders
* Website is open to the public, and anyone can use it

## Test Approach
From the risk analysis, these test approaches are planned  

* API testing on each endpoint: Automated
   * Focus on data validity 
* UI testing on each feature
   * Scripted test on each screen
   * Exploratory test to find user issues
   * Test major features on multiple browsers

And the test scope is set to **Functional Testing**.

## Automated Testing
These critical functionalities were tested by automated testing.
1. **Displaying Most Popular Make and Model on dashboard screen**
   * User wants to see the most popular car, right away when they visited the website. It is most critical part of the website to display the correct detail of the most popular make and model to users.
2. **User Registration and Login**
   * This is the website that users can vote. It is important to manage users and make sure they can vote only when they are logged in.
3. **Vote for model**
   * User should not vote more than once per model, in order to prevent abuse. Also, it is important that my vote is applied correctly, and users want their comments to be viewed by other users.
4. **View Overall Rating**
   * User wants to compare different models' popularities. It is critical to provide features that users can sort the models.
5. **View Model Detail**
   * User wants to see the correct details of the cars they are interested, as well as comments of the model.

## Test Result

### Test Summary
* API test (total 17 test cases)
   * 15 success
   * 2 failed  

* UI test (total 20 test case runs)
   * 17 success
   * 3 failed

* Total 11 issues were found during testing
   * 5 major
   * 6 minor

### Detailed test result
* [Test Result - Google Spreadsheet](https://docs.google.com/spreadsheets/d/1Q3gF7bouFEos2vCjT5rP6gCY0FsSpFSv0a8Cp8DL39M/edit?usp=sharing)
    * This contains:
       * Automated Test result
       * Manual Test result
       * Exploratory Test charter
* [Issue List - Google Spreadsheet](https://docs.google.com/spreadsheets/d/1wQ7vfWdHb8VA9Orgrr1lm8XHj6jZQmC5SCcxfTlXkqs/edit?usp=sharing)
    * This contains:
       * Issue list
       * Issue details


## Exclusion
This test practice focus on functional testing and these non-functional tests were excluded.
* Usability testing
* Accessibility testing
* Security testing
* Load testing
