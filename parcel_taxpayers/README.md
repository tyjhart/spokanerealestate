# Parcel Taxpayer Analysis

Discussion [continues online](https://www.reddit.com/r/Spokane/comments/b6pb4z/spokane_ranked_83rd_most_expensive_city_to_live_in/) about real estate and rental markets in Spokane. We're experiencing historically-low vacancy rates for rentals and a fast-paced sales market driven by demand that isn't satisfied by available inventory. Both have caused rents to rise and sale prices to inflate in the greater Spokane area. Speculation around the cause of low vacancy rates and rising prices tends to center around a few theories:

1. Zoning laws prohibit new construction that would satisfy demand
1. Existing residents are resistant to development in their neighborhood
1. An influx of buyers from more expensive markets (CA, east coast, etc.) willing to pay more are pulling the market upward
1. Investors from outside the area buying up properties for investment / rentals are reducing inventory for local residents looking to buy

Issues with zoning have been explored by local journalists and researchers. Anecdotal evidence of residents resistant to change has been featured in articles by the Inlander and Spokesman Review. These are difficult to quantify and visualize, and I don't want to turn this small project into an opinion piece. 

What I want to do is analyze who owns parcels of land in Spokane. Do locals own most of the parcels in our county? If so, how much of it do they own? How many parcels are owned by out-of-towners? Has there been investment in real estate from overseas? We'll have a look.

## Assumptions & Challenges

The assumption that an out-of-state taxpayer address means the owner is from elsewhere won't always be true. Trusts, investment corporations, and other entities that own parcels have registered addresses that may or may not reflect locations of people behind the organization. For example, a popular option for incorporating is to register a business in Deleware, given that state's favorable tax environment and unique legal structures. Residents of Spokane could easily incorporate a Deleware LLC and purchase properties as that organization. Spokane's taxpayer records would show a parcel's taxes being paid from a Deleware address, even though the actual owner is local. 

My family's situation is unique as well; We purchased property in Spokane and used it initially as our primary residence. Then I got a good job offer from a company in Virginia and we relocated to the east coast. Now in Spokane's recent tax records I am an out-of-state owner, even though I was originally a local buyer. It's also difficult to determine if the reverse has happened. Buyers (taxpayers) from out-of-state who move to the area aren't recorded as such when purchasing a home for their primary residence; Spokane county's downloadable data doesn't include information about the purchaser's residency. 

We also can't account for "snowbirds" who may have moved their primary residence out-of-area, but occupy local homes part-time. These people were originally local buyers, and should be accounted for as-such, but we have no way to know who that situation applies to. There is certainly a cadre of snowbirds in the local area, but estimating their size with any amount of accuracy is not feasible with the data at-hand.

Despite these challenges I think the taxpayer data is interesting, and we shouldn't "sacrifice the good for the perfect" when it comes to exploratory data analysis (EDA). There are over 300,000 rows of data on Spokane County parcel taxpayers. Given that amount of data and the number of unique taxpayers listed in the county, I'm comfortable drawing some basic conclusions about parcel ownership.

## Data Restrictions

There is something important to note about the data - while it is freely-available, Washington state law forbids lists of people derived from this data being used for commercial reasons:

>RCW 42.56.070(9) prohibits the release of lists of individuals requested for commercial purposes. The requester expressly represents that no such use of any such list will be made by the user or its transferee(s) or vendee(s).

During analysis I won't be referrencing the names of individuals at all. We only care about their location (country, state, city) and parcel number for the purposes of this project.