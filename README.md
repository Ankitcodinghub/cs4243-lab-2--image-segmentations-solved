# cs4243-lab-2--image-segmentations-solved
**TO GET THIS SOLUTION VISIT:** [CS4243 Lab 2- Image Segmentations Solved](https://www.ankitcodinghub.com/product/cs4243-lab-2-image-segmentations-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;113960&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;1&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (1 vote)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS4243  Lab 2- Image Segmentations Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (1 vote)    </div>
    </div>
Objective

In this lab you will implement image segmentation with K-means and mean-shift algorithms.

Part 1: Image Prepossesing (5%)

Implement following function: smoothing().(3 points)

Implement following function: RGBtoLab().(2 points)

Part 2: Clustering (80%)

In part 2, you will implement K-means and mean-shift clustering algorithms.

2.1 K-Means Clustering

The basic idea of K-Means algorithm is to randomly initialize the k cluster centers, and iterate between assigning membership and computing cluster centers. For our setting, assume the input data are P = {p1, …, pn}, for each pi ∈ Rd. n is the number of points, d is the number of features.

1. Randomly pick k points from P as the centers: ci, c2, …, ck ∈ Rd

2. Iterate the process until max iterations or centers are no longer change up to some threshold:

i. Assign each point to nearest center:

yi = argmin ||pi − cj||2

j

pi

cj :=

1(yi == j) is the indicator function which equals 1 if point i belong to cluster j, 0 otherwise.

Implement following function: k means clustering().

Prohibited function: cv2.kmeans().

2.2 Mean Shift Clustering

The main idea behind mean shift clstering is to find modes or maxima in the local density function in the feature space for each pixel. To achieve this, mean shift iteratively computes the mean of all the pixels that lies within a spherical window of certain radius and shifting the window center to the mean until convergence (until max iterations or centroids stop moving up to some threshold).

The steps are:

1. Generate windows by tessellating. We also call the center of these windows ‘bin seeds’, which means it’s the starting point for each mean shift thread. For the sake of simplicity and time complexity, we will do tessellating by following steps:

i. For all points, compress all coordinates within square of bandwidth length into one coordinates:

Compute

np.round(X/bandwidth, Y/bandwidth)

for all the points.

ii. Group pixels with same value, suppose the value is um ∈ Rd. Compute the total number Num of points belong to this group. we also call um the seed of this group.

iii. For all the seeds u1, u2, …, um, check the total number of points belong to this seed, filter out all the seeds with total number less than the threshold.

Num ≥ min bin freq

min binfreq is used to drop out-liners with low density, in this lab we use min bin freq=1, means that we do not drop any points when we do tessellating.

iv. Multiply bandwidth to reproject seeds to original size and return all the seeds as a list.

um ∗ bandwidth

Here’s the graph illustrating these steps. Each color represents a bin seed.

Implement following function: get bin seeds().

The reason why we use squares instead of spheres is because computing sphere needs more computations. Also for the seeds, we do not use random sampling because it tends to give us more points at high density area. In case we only want a reasonable starting point set which can cover most of the space that distribution span. It’s quite enough.

2. Now we can run standard mean shift algorithm for each seed. Here you need to implement single thread mean shift for one starting point.

1. Iterate following steps until convergence to find peak.

ii. Compute mean of all points within, shift center of window to new mean.

2. Return peak and total number of points within bandwidth of the peak.

Implement following function: mean shift single seed().

3. Complete mean shift pipeline. Run mean shift single seed in parallel. Merge peaks within bandwidth. Assign points to the closest cluster peak.

i. We already run parallel mean shift for you in the code. You now have a dict center intensity dict for all the peaks. The key is the tuple of peak coordinates, the value is the number of points within bandwidth of the peak.

Implement following function: mean shift clustering().

Prohibited function: cv2.meanShift.

Part 3: Image Segmentation (15%)

Use functions you implemented above to do image segmentation. You should first reshape image to meet input format. And to get a better result, you should tweak k for K-means and b for mean shift. We also provide more pictures for you to test your implementation.

Implement following function: k means segmentation().

Implement following function: mean shift segmentation().

Hand in
