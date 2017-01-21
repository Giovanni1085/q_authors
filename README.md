# q_authors

A partial replication of Sinatra, R., D. Wang, P. Deville, C. Song, and A.-L. Barabasi. “Quantifying the Evolution of Individual Scientific Impact.” Science 354, no. 6312 (November 4, 2016), doi:10.1126/science.aaf5239.
URL: http://science.sciencemag.org/content/354/6312/aaf5239.
Supplementary materials: http://science.sciencemag.org/content/suppl/2016/11/02/354.6312.aaf5239.DC1?_ga=1.178615011.657974594.1453296229.

# Contents

* `Replication.ipynb` The code to replicate some of the figures in Sinatra et al. 2016. Shows figures 1E, 2B, 2A.
* `Simulations.ipynb` The notebook to simulate part of the results. Show the lack of difference in plot 2B if the impact of articles comes from a power law or a uniform distribution.
* `LICENCE` MIT
* `README.md` this file
* SupplementaryDataSinatra2016/
    * `APS_author2DOI.dat` list of author name disambiguation and related articles, from the Supporting materials
    * `readme.txt` from the Supporting materials
    * `sinatra_Science_id_studied.dat` list of author ids used in the article, from a private communication
* Dataset/
    * `author_index_all_month.p`
        * A dictionary with all the authors in the APS dataset (origins to 2010) which have at least 1 article with a 10y lifetime, thus published before 2000 taking 2010 as the last useful year.
        Every article is considered, provided it has a date and has a lifetime of at least 10y. The list of authors comes from the supplementary materials of the article (file APS_author2DOI.dat).
        This dataset was created using the APS dataset, available here: http://journals.aps.org/datasets.
        * Every author has the following infos (the index is equal to the field `id` below):
                `{'articles': [{'c_ten': 8,
                   'date': '1949-09-15',
                   'id': '10.1103-PhysRev.76.854',
                   'year': 1949},
                  {'c_ten': 6,
                   'date': '1953-10-15',
                   'id': '10.1103-PhysRev.92.441',
                   'year': 1953}],
                 'c_ten_star': 8,
                 'first_year': 1949,
                 'id': 0,
                 'in_core': False,
                 'last_year': 1953,
                 'surface': 'p.  bassi'}`
            * `articles` is a list of articles, each containing the number of citations received after 10 years (c_ten, or impact), the date and year of publication, the identifier.
            * `c_ten_star` is the impact of the most impactful article for the given author
            * `first_year` and `last_year` of activity of the author
            * `id` its ID from APS_author2DOI.dat, first column
            * `surface` the surface form of the author, as found in the APS dataset
            * `in_core` if the author meets the requirements to be considered in the dataset of the article. These requirements are: at least 10 publications, an activity span of at least 20 years, no more than 5 years between publications. Despite several attempts, the filtering of the original APS dataset to the authors analysed in Sinatra et al. was not possible, hence the authors kindly supplied the list ot be used as a filter (sinatra_Science_id_studied.dat)

# Dependencies

Python 3.5
Numpy, Scipy, Pickle

