# Assignment
While the influencers who use our platform are really great at taking selfies, most aren't super great at math. We need to write a tool that predicts an influencer's follower growth over time.


Complete the __get_follower_prediction__ function. It takes a __follower_count__ integer, an __influencer_type__ string and a __num_months__ integer, and returns an integer.

------

Calculate the number of followers an influencer will have after a given number of months according to the influencer type:

- __"fitness" :__ follower count quadruples each month
- __"cosmetic" : __ follower count triples each month
- __other :__ follower count doubles each month

***

For example, if a __"fitness"__ influencer starts with .__10__ followers, then after __1__ month they would have __40__ followers. After __2__ months, they would have __160__ followers, and so on.

This kind of sequence, where each term is found by multiplying the previous term by a constant, is called a geometric sequence or [geometric progression](https://en.wikipedia.org/wiki/Geometric_progression).

Use the following version of the geometric progression formula, in which __a1__ is the initial number of followers, __r__ is the multiplication constant, and __n__ is the number of months:

> total = a<sub>1</sub> × r <sup>n</sup>


```
def get_follower_prediction(follower_count, influencer_type, num_months):

    # Determine the multiplication constant (r) based on the influencer type

    if influencer_type == "fitness":
        r = 4

    elif influencer_type == "cosmetic":
        r = 3

    else:
        r = 2
        

    # Calculate and return the geometric progression: a1 * r^n
    return follower_count * (r ** num_months)
```