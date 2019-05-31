# pet_adoption_prediction
Project to analyze adoption trends from the Austin Humane Society.

I. Definition
By estimates from the ASPCA, there are over 6.5 million animals entering animal shelters each year in the United States, and of those 1.5 million animals are euthanized, 3.2 million are adopted, and 720,000 are returned to their owners. Animal shelters provide many services to pet owners, from rehoming pets and providing owners adequate resources to help train and care for them, to returning lost pets to their original owners, and in the case of a no-kill shelter, caring for the animal until the end of its life.   
Usually no-kill shelters are closed admission, which means they do not have a representative animal population, as animals deemed incapable of rehabilitation are turned away.  The Austin Shelter is an exception to this, as it is no-kill to the 90% threshold, and as such does perform euthanasia in extreme cases.  These open admissions shelters will not euthanize an animal just for space except under extreme conditions, and sometimes pets are housed in the shelter for up to a year.  The Austin Shelter seems to be well funded in comparison to other municipal shelters, and they have partnered with outreach organizations, have Facebook posts, and 24 hour warning notifications of animals scheduled for euthanasia, so they may be an example of the best outcome for animals that find their way to the shelter. 
The following links were used as sources for this domain background. 

https://www.aspca.org/animal-homelessness/shelter-intake-and-surrender/pet-statistics
https://www.elephantjournal.com/2015/09/kill-vs-no-kill-shelters-the-great-debate/ http://www.austintexas.gov/sites/default/files/files/Animal_Services/aac_no_kill_implementation_plan.pdf 


II. Methodology

Data Preprocessing

The data from intakes_outtakes_data.csv contained all the information required.  The first question posed was what to do with animals that had been to the shelter in the past, sometimes multiple times in the past.  The data was sorted by the time admitted, and a new field was created on subsequent shelter visits after the first visit.  Using this, all entries could be retained rather than just looking at the most recent visit.   The second item to consider was whether all animals needed to be examined.  National data is limited to dogs and cats, so other wildlife and animal types were removed.
Because animals are required to be kept for 72 hours, only entries for animals staying longer than 72 hours were retained, as the decision to euthanize would be made at that time at a kill shelter.
Breed, color, and surrender type were transformed with get_dummies into flags.  In addition, the surrender type and dog age were retained, as well as the month of intake, to account for seasonality.
We limited the scope to normal intake, as abnormal intake would require more resources and would be lower priority at high kill shelter.  
Some data did not possess valid information in the entries, and these were discarded.  The discarded entries represented TBD% of the data, and the distribution after discarding was unchanged. See table.

How to handle transfers

III. Results
