# Finding the Best Candy
Selecting a variety of candies that appeal to everyone is a challenging task, as taste is inherently subjective. However, by leveraging data, we can find some solutions to this problem. In this project, I have endeavored to do just that.
# Data Set
The dataset contains various attributes of different candies, including the number of flavors—such as chocolate, caramel, fruit, almond, rice, and crisp. Additionally, it features metrics like sugar percentage, price percentage, and win percentage, which reflects the outcome of overall preferences based on 269,000 random matchups.
# Analyzing the Data
Upon initial analysis, I discovered that the data varied significantly in scale. For instance, the range of values for win percentage was between 0 and 100. Consequently, I normalized the win percentage to a range between 0 and 1.
At first glance, the win percentage appeared to be the simplest and most straightforward metric for evaluating candies. However, relying solely on this metric may not fully capture everyone's preferences, as it is derived from random matchups. Nevertheless, it does indicate general popularity among consumers. Therefore, I aimed to develop a scoring system that incorporates all features of each candy.
To achieve this, I calculated the total number of flavors for each candy, ensuring that those with a higher flavor count received a better flavor score. This value was also normalized to fall between 0 and 1. I observed a correlation of 0.61 between the normalized number of flavors and normalized win percentage, while sugar percentage and price percentage had lower correlations of 0.23 and 0.56, respectively.
With these metrics in mind, I selected four features to compute a score for each candy, assigning weights based on my objectives. The formula I employed is as follows:

  ## Weighted_score=(0.2×sugarpercent)+(0.2×flavor_count)+(0.2×(1−pricepercent))+(0.4×winpercent)
  
In this formula, winpercent is weighted most heavily at 40% because it directly reflects the candy's popularity, which is our primary focus. The other features are included to ensure we cater to diverse tastes. The price percentage is subtracted from 1 to emphasize that lower prices enhance purchasing power, enabling us to distribute more candies.
These considerations reveal that the Weighted Score has a nearly linear relationship with win percentage, as shown on the dashboard. Additionally, slicers have been integrated to accommodate personal preferences, allowing users to choose between bar or hard candies.
Based on this analysis, my top three candy recommendations for Halloween are:
 - Snickers
 - Reese's Stuffed with Pieces
 - Milky Way Midnight
