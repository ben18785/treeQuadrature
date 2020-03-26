Methods for diagnosing poor calculation:

* The peeling method provides a useful plot for diagnosing whether there is a reasonable answer to the integral:
  * This may also suggest more intelligent ways of estimating the integral (for example, looking for plateaus)
* Cumulative volume vs cumulative contribution helps visualise lumpy bits (where we first order by smallest volume to largest)
* If you have an idea of the posterior, sampling from the containers is informative: for the MVT normal case:
  * it is clear that the tails are over-contributing for $D\geq 3$
  * it is clear from pairwise scatterplots that we are getting some weirdly shaped boxes: SEE THE ST. GEORGE'S CROSS FOR D=5! AARRGH
* Even if you don't have a posterior, unless your "container samples" look like your actual samples, then you may struggle with integrals without peeling

Questions:

* Can we peal away outside shell? I think this is similar to what I am doing with removing the biggest boxes
* Perhaps better, can we try the method described in Weinberg 2012 S3.2? Although, I have no idea what he does! ("A remarkably simple and accurate method for computing the Bayes Factor from a Markov chain Monte Carlo Simulation of the
  Posterior Distribution in high dimension")
* For multiple modes, why not run k-means (or some other clustering algorithm) to partition samples to modes, then run integration on each mode separately? Probably want a fairly strong prior on number of clusters being close to 1 to avoid the case where modes are very close and overlap
* We should probably try an integral with fat tails, like a Student t with *just* enough degrees of freedom that it has a mean