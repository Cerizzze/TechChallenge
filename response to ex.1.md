# Response to exercise 1  

*I will assume this thumbnail ![alt text](https://raw.githubusercontent.com/Cerizzze/TechChallenge/master/obtained%20reward.PNG "obtained reward") means that a reward has been obtained but not claimed yet and this button ![alt text](https://raw.githubusercontent.com/Cerizzze/TechChallenge/master/claiming%20button.PNG "claiming button") means that an already obtained and claimed reward can be claimed once again.*

--------------------
**Feature**: Front-End Rewards history in Freebies Vault Section

**As** a user  
**I want** to access my rewards history in the Freebies Vault section  
**In order to** see my obtained and claimed rewards  

**Scenario**: Display "your history" section when a reward is claimed  
**Given** user is logged in  
**And** has claimed and obtained at least one token  
**When** user goes to the Freebies Vault section  
**Then** the “your history” section is displayed and reachable  
**And** user can see the claimed and obtained token(s)  

**Scenario**: Display one characteristic thumbnail for each token  
**Given** user is logged in  
**And** has already claimed and obtained several different tokens  
**And** didn't claim all of them  
**When** user goes to Freebies Vault / “your history” section  
**Then** user can see 1 characteristic thumbnail displayed for each token  
**And** a specific thumbnail for unclaimed tokens  

**Scenario**: Display only the last 8 obtained and claimed tokens in the Freebies Vault/"your history" section  
**Given** user is logged in  
**And** has obtained and claimed at least 9 tokens  
**When** user goes to Freebis Vault/your history section  
**Then** user can only see the 8 last obtained and claimed tokens displayed  

**Scenario**: Display claiming button when a token can be claimed once again  
**Given** user is logged in  
**And** has already obtained and claimed one specific token (token A)  
**And**obtained once again token A whithout claiming it  
**When** user goes to Freebies Vault / “your history” section  
**Then** user can see a claiming button displayed on token A's thumbnail  

**Scenario**: Display name of the game when hovering the mouse over a token  
**Given** user is logged in  
**And** has claimed and obtained several tokens  
**And** goes to Freebis Vault / “your history” section  
**When** user hovers the mouse over a token  
**Then** the name of the game where the token was obtained from is displayed above the thumbnail 

--------------------

**Feature**: Back-End Rewards history in Freebies Vault Section  				

**As** a back-end developer  
**I want** to use the method `/igc/betspin/rewards/history` with only 1 param `userName`  
**In order to** access user's reward history data "					
					
**Scenario**: Get reward history data per user  
**Given** an user already claimed several rewards  
**And** claimed more than once the same reward  
**When** using the method `/igc/betspin/rewards/history` with only 1 param `userName`  
**Then** I see a JSON with an array of unique tokens claimed by that user chronologically ordered  
**And** I see sub-array objects chronologically ordered for each unique tokens claimed more than once  
**And** I get for each sub-array objects the followings:  
 * game-slug  
 * date claimed  
 * info  
 * reason  
 * expiration date  
