
## happy path               <!-- name of the story - just for debugging -->
* greet              
  - utter_greet
* mood_great               <!-- user utterance, in format intent[entities] -->
  - utter_happy
* mood_affirm
  - utter_happy
* mood_affirm
  - utter_goodbye
  
  
## sad path 1               <!-- this is already the start of the next story -->
* greet
  - utter_greet             <!-- action the bot should execute -->
* mood_unhappy
  - utter_cheer_up
  - utter_did_that_help
* mood_affirm
  - utter_happy

## good purchase path               <!-- name of the story - for making purchase-->
* greet              
  - utter_greet
* mood_great               <!-- user utterance, in format intent[entities] -->
  - utter_happy
* mood_affirm
  - utter_happy
* purchase                  <! -- user intention to purchase things --->
  - utter_purchase  
* purchase_affirm           <!-- user utterance, in format intent[entities] -->
  - utter_purchase
  - utter_ask_item
  - utter_show_item
* purchase_affirm
  - utter_price
* mood_affirm
  - utter_goodbye
  
## good purchase path2
* greet              
  - utter_greet
* inform                    <!-- user utterance, in format intent[entities] -->
  - utter_ask_item
  - utter_show_item
  - utter_did_that_help
* goodbye
    - utter_goodbye

## no purchase path               <!-- name of the story - for making purchase-->
* greet              
  - utter_greet
* mood_great               <!-- user utterance, in format intent[entities] -->
  - utter_happy
* mood_affirm
  - utter_happy
* purchase                  <! -- user intention to purchase things --->
  - utter_purchase  
* purchase_deny           <!-- user utterance, in format intent[entities] -->
  - utter_purchase
* purchase_deny
  - utter_ask_item
* mood_affirm
  - utter_goodbye
  
  
## get weather of location
* greet
  - utter_greet
* mood_great               <!-- user utterance, in format intent[entities] -->
  - utter_happy
* inform
  - utter_ask_location
* inform{"location": "Paris"}
  - utter_ask_location
* goodbye
    - utter_goodbye
    - export
    
## get weather of location
* greet
    - utter_greet
* inform[location=London]
    - utter_ask_location
* goodbye
    - utter_goodbye
    - export
  
  
## strange user
* mood_affirm
  - utter_happy
* mood_affirm
  - utter_unclear

## say goodbye
* goodbye
  - utter_goodbye

