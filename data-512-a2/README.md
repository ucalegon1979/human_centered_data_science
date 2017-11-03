## data-512-a2: DATA 512 Assignment 2: Bias

## __Project Goals__

The goal of this project is to highlight biases found in data about Wikipedia articles. Specifically we will compare the proportion of "good" articles to each countries population.

To do this we will download page data, using a special REST API, called ORES, from Wikimedia to get the page quality for each article by sending its revision ID. After that is done, we can aggregate the data by country, pair with population data from each country and then perform our analysis.

## __Software Requirements__

Python 3.0 at a minimum is required to run the project. Additionally you will need to be able to import the following libraries in order to load, transform, call the API. The following are import statements required to run the code.

    import requests
    import pandas
    import json
    
In order to run the code from the ipynb notebook file, you will also need Jupyter Notebook.

## __Data__

The population data was gleaned from the Population Research Bureau [website](http://www.prb.org/DataFinder/Topic/Rankings.aspx?ind=14)

#### Copyright

The Wikipedia article quality data was collected from the Wikimedia ORES ("Objective Revision Evaluation Service") REST API, 
Wikimedia Foundation, 2017. CC-BY-SA 3.0. 

#### License

This Wikimedia Foundation data is licensed under an Apache 2.0 License, which includes in part:  

> Unless required by applicable law or agreed to in writing, software  
> distributed under the License is distributed on an "AS IS" BASIS,  
> WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.  
> See the License for the specific language governing permissions and  
> limitations under the License.  

For more information on this license, see [Apache 2.0 License](http://www.apache.org/licenses/LICENSE-2.0).

#### Terms of Use

The use of Wikipedia data is subject to the Wikimedia Foundation Terms of Use (TOU). A summary of these TOU, along with the complete terms are available [here](https://wikimediafoundation.org/wiki/Terms_of_Use/en). 

### ORES API Documentation

The Objective Revision Evaluation Service, aka ORES documentation is found [here](https://www.mediawiki.org/wiki/ORES). 

This API can be given many revision IDs of articles simultaneously to efficiently produce a dataset containing the rating
of each article. 
 
Each article is rated on the following scale, ordered from best to worst:

1. FA - Featured article
2. GA - Good article
3. B - B-class article
4. C - C-class article
5. Start - Start-class article
6. Stub - Stub-class article

### Wrangling

The page data is fed, or at least the revision IDs are fed, to the ORES API. 
The article quality is then added as a new column in that dataset.

Next, this data is aggregated up to the country-level, so that it can be joined to the population data by country.

Finally some descriptive statistics are created to show the relative proportions of good articles to each countries population, etc.

### Analysis

The final analysis of this data is presented in four crosstabs showing the top 10 of each of the following questions. 

1. Number of politician articles / country population, ranked in descending order, displaying the highest-ranked countries.
2. Number of politician articles / country population, ranked in ascending order, displaying the lowest-ranked countries.
3. Number of FA or GA articles / country population, ranked in descending order, showing the best countries.
4. Number of FA or GA articles / country population, ranked in ascending order, showing the lowest-ranked countries.

### Final Result

The final page data matched with the article quality is stored in the page_data_responses.csv file.

## __File Manifest__

1. hcds-a2-bias.ipynb - A Jupyter Notebook file containing all the code to reproduce the results from this project.
2. README.md - this file.
3. LICENSE - MIT license explaining terms of use.
4. page_data_responses.csv - A comma-separated values (CSV) file containing the article data, coupled with page ratings from the ORES API.