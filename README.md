# H and M-Recommender-System

<h1 style="background-color:#f7e9ec;font-family:newtimeroman;color:#d90b1c;">Terminologies</h1>

<p>There are certain terminologies which needs to be understood before moving forward.</p>

<ul>
    <li><strong>Apache Spark:</strong> Apache Spark is an open-source distributed general-purpose cluster-computing framework.It can be used with Hadoop too.</li>
    <li><strong>Collaborative Filtering:</strong> Collaborative filtering is a method of making automatic predictions (filtering) about the interests of a user by collecting preferences or taste information from many users. Consider example if a person A likes item 1, 2, 3 and B like 2,3,4 then they have similar interests and A should like item 4 and B should like item 1..</li>
    <li><strong>Alternating Least Squares (ALS) Matrix Factorization:</strong> The idea is basically to take a large (or potentially huge) matrix and factor it into some smaller representation of the original matrix through alternating least squares. We end up with two or more lower dimensional matrices whose product equals the original one.ALS comes inbuilt in Apache Spark.</li>
    <li><strong>PySpark:</strong> PySpark is the collaboration of Apache Spark and Python. PySpark is the Python API for Spark.</li>
</ul>
<h2> EDA </h2>
<h1 style="background-color:#f7e9ec;font-family:newtimeroman;color:#d90b1c;text-align:center;border-radius:10px 10px;border-style:solid;border-color:#d90b1c;">
    Exploratory Data Analysis (EDA) on H&M Fashion Dataset
</h1>

<h2 style="color:#3e0542;">1. Importing Libraries</h2>
<p>The necessary Python libraries for data manipulation, visualization, and machine learning are imported:</p>
<ul>
    <li><strong>numpy</strong> and <strong>pandas</strong>: For numerical operations and data handling.</li>
    <li><strong>seaborn</strong> and <strong>matplotlib</strong>: For visualization.</li>
    <li><strong>plotly</strong>: For interactive plots.</li>
    <li><strong>datetime</strong>: For handling time-based data.</li>
    <li><strong>matplotlib.image</strong>: To load images.</li>
</ul>

<h2 style="color:#3e0542;">2. Loading and Understanding Data</h2>
<p>Datasets loaded:</p>
<ul>
    <li><strong>articles.csv</strong>: Contains article details like product type, color, department, etc.</li>
    <li><strong>customers.csv</strong>: Contains customer demographic details.</li>
    <li><strong>transactions_train.csv</strong>: Contains purchase history.</li>
</ul>
<p>The shape of each dataset (number of rows and columns) is displayed.</p>
<p>Customer engagement analysis includes:</p>
<ul>
    <li>Number of customers who made at least one purchase.</li>
    <li>Percentage of inactive customers.</li>
</ul>

<h2 style="color:#3e0542;">3. Checking for Missing Values</h2>
<p>Missing values in the transaction dataset are counted using <code>.isna().sum()</code>.</p>

<h2 style="color:#3e0542;">4. Articles Sold Analysis</h2>
<ul>
    <li>Grouped by date (<code>t_dat</code>), the number of articles sold per day is computed.</li>
    <li>A time-series line plot is created to show the trend of articles sold from <strong>2018-09-20 to 2020-09-22</strong>.</li>
    <li>Notable spikes are identified, with <strong>2019-09-28</strong> being the highest sales day.</li>
</ul>

<h2 style="color:#3e0542;">5. Transaction Amount Analysis</h2>
<ul>
    <li>Total sales per day are aggregated and plotted.</li>
    <li>The highest transaction amount was recorded on <strong>2019-09-28</strong>.</li>
    <li>A <strong>25% drop</strong> in transaction amount is observed on <strong>2019-11-29</strong>.</li>
</ul>

<h2 style="color:#3e0542;">6. Top Customers Analysis</h2>
<ul>
    <li>Customers who made the most transactions are identified and displayed in a table.</li>
    <li>The <strong>top 10 customers</strong> made more than <strong>1,000 purchases</strong>.</li>
</ul>

<h2 style="color:#3e0542;">7. Articles Sold by Age Distribution</h2>
<ul>
    <li>Customer ages are merged with transaction data.</li>
    <li>A histogram is plotted, showing that most buyers are between <strong>21 and 39 years old</strong>.</li>
</ul>

<h2 style="color:#3e0542;">8. Articles Sold by Sales Channel</h2>
<ul>
    <li>Sales are analyzed by <strong>Sales Channel ID (1 or 2)</strong>.</li>
    <li><strong>Sales Channel 2</strong> has consistently higher sales.</li>
    <li>Missing transaction periods for <strong>Sales Channel 1</strong> are identified.</li>
</ul>

<h2 style="color:#3e0542;">9. Transaction Amount by Sales Channel</h2>
<ul>
    <li>The total transaction amount is analyzed by sales channel.</li>
    <li><strong>Sales Channel 2</strong> records the highest transaction amounts.</li>
    <li>Missing transaction periods are noted for <strong>Sales Channel 1</strong>.</li>
</ul>

<h2 style="color:#3e0542;">10. Articles Sold by Product Group</h2>
<p>Articles are grouped by product group and visualized.</p>
<p><strong>Ladieswear</strong> is the most dominant category, followed by a mix of others.</p>

<h2 style="color:#3e0542;">11. Articles Sold by Department</h2>
<p>Articles are grouped by department name and displayed in a bar chart.</p>
<p><strong>Swimwear, trousers, and blouses</strong> are the most frequently purchased items.</p>

<h2 style="color:#3e0542;">12. Articles Sold by Color</h2>
<p>The most popular color for purchased articles is <strong>black</strong>.</p>

<h2 style="color:#3e0542;">13. Articles Sold by Garment Type</h2>
<p>The most sold garment group is <strong>Jersey (fancy & basic)</strong>.</p>

<h2 style="color:#3e0542;">14. Fashion News Frequency</h2>
<p>Most customers do not receive regular fashion news updates.</p>

<h2 style="color:#3e0542;">15. Club Member Status</h2>
<p>The majority of customers have <strong>active memberships</strong>.</p>

<h2 style="color:#3e0542;">16. Word Cloud for Product Descriptions</h2>
<p>A <strong>word cloud</strong> is generated using <code>WordCloud</code> to highlight common product description words.</p>

<h2 style="color:#3e0542;">17. Mean Price for Articles</h2>
<ul>
    <li>The <strong>average price</strong> of various product groups over time is analyzed.</li>
    <li>A <strong>time-series plot</strong> shows price trends.</li>
</ul>

<h2 style="color:#3e0542;">18. Top 5 Most Expensive & Cheapest Articles</h2>
<ul>
    <li>The <strong>top 5 most expensive</strong> and <strong>top 5 cheapest</strong> articles are identified.</li>
    <li>Their images and descriptions are displayed.</li>
</ul>

<h2 style="color:#3e0542;">19. Final Notes</h2>
<ul>
    <li>A link to the <strong>Kaggle notebook</strong> is shared.</li>
    <li>Users are encouraged to <strong>comment, provide suggestions, and upvote</strong> if they find the analysis useful.</li>
</ul>

<h2 style="color:#3e0542;">Key Insights</h2>
<ul>
    <li><strong>2019-09-28</strong> had the highest sales and transaction amount.</li>
    <li><strong>Sales Channel 2</strong> dominates in sales and revenue.</li>
    <li>Most buyers are between <strong>21-39 years old</strong>.</li>
    <li><strong>Black</strong> is the most popular color.</li>
    <li>Many customers do not receive fashion news.</li>
    <li><strong>Jersey garments</strong> and <strong>ladieswear</strong> are highly preferred.</li>
</ul>
