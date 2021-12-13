# Election Audit

## Overview
Requested to complete an election audit on a congressional election. The client wanted to know:
1. Calculate the total number of votes cast
2. Calculate the Voter turnout for each county
3. Calculate the percentage of votes from each county out of the total count
4. Calculate the county with the highest turnout
5. Get a complete list of candidates who received votes
6. Calculate the total number votes each candidate received and percentage of votes each candidate won
7. Determine the winner of the election based

## Results
* How many votes were cast in this congressional election?
    - There was a total of 369,711 votes cast
* Breakdown of votes and percentage of total votes for each county
    - ![County_Votes](https://github.com/Drakeblaze10/Election-Analysis/blob/main/Resources/County%20votes.PNG)
* County with the largest number of votes
    - Denver
* Breakdown of number of votes and percentage of total votes for each candidate
    - ![Candidate_votes](https://github.com/Drakeblaze10/Election-Analysis/blob/main/Resources/Candidate%20Votes.PNG)
* Which candidate wont the election
    - Diana Degette won the election, with 272,892 votes, which makes up for 73.8% of all votes

## Summary
The script is easily adaptable for any election. If the format of the data is the same it can adapt very easily to the number of candidates and number of counties. If, however, you wish to do something along the lines of including states or cities you can copy and paste the following lines to accomadate the additional rows:
- city_names = row[ ]
-  #If the candidate does not match any existing candidate add it to
        # the candidate list
        if candidate_name not in candidate_options:

            # Add the candidate name to the candidate list.
            candidate_options.append(candidate_name)

            # And begin tracking that candidate's voter count.
            candidate_votes[candidate_name] = 0

        # Add a vote to that candidate's count
        candidate_votes[candidate_name] += 1

        # 4a: Write an if statement that checks that the
        # county does not match any existing county in the county list.
        if county_names not in county_options:

            # 4b: Add the existing county to the list of counties.
            county_options.append(county_names)

            # 4c: Begin tracking the county's vote count.
            county_votes[county_names] = 0

        # 5: Add a vote to that county's vote count.
        county_votes[county_names] +=1
  #Save the final candidate vote count to the text file.
    for candidate_name in candidate_votes:

        # Retrieve vote count and percentage
        votes = candidate_votes.get(candidate_name)
        vote_percentage = float(votes) / float(total_votes) * 100
        candidate_results = (
            f"{candidate_name}: {vote_percentage:.1f}% ({votes:,})\n")

        if (votes > winning_count) and (vote_percentage > winning_percentage):
            winning_count = votes
            winning_candidate = candidate_name
            winning_percentage = vote_percentage
By changing the variables to include cities or states and the additional row you can specify which row you want to pull from. By adding new variables and inputing them into these lines you can specify down to any variable.
Another point I noticed is that this data does not include the total number of potential voters. It only includes data of votes cast. By including potential voters into the data one could ascertain where to focus their campaigning efforts in either locations with the highest voter turnout or to focus on locations with the least in the hopes of increasing their turnout in favor of your campaign.      