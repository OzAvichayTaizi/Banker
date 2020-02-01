# Banker

The defualt campaigns will upload in setup via "getCampaigns" function.
"getCampaigns" return hashmap.  
Key is type long that represent id of campaign and
value is type long that represent money of campaign.

The campaigns data can only change via "DataCampaignsConfig" class

Redis db use in port 6379 and host localhost you can change those 
properties via application properties file.

The server run on port 9119  you can also change this via application properties file.

There is two api :

@PostMapping("/bid")
public Boolean newBid(@RequestBody Bid newBid)

post request get Bid as json object 

like this
{
	"bidId":1,
	"campaignId":3,
	"cost":2
}

This api give indication if there is enough money on server memory
and reduce money in case a bid happens.

The second api is to get the answer of the result of bid
@PostMapping("/bid/{id}/{status}")

post request get bid id and status (WIN,LOSE)
and update accordingly the server budget.


