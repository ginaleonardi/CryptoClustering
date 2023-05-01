# CryptoClustering
Unsupervised learning with Python, Pandas, and scikit-learn
 <div class="description user_content "><div id="bootcamp">
<img style="display: none;" src="https://static.bc-edx.com/data/dl-1-2/m19/lms/img/banner.jpg" alt="lesson banner">
    <p>In this challenge, you’ll use your knowledge of Python and unsupervised learning to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.</p>
    <h3>Before You Begin</h3>
    <ol>
        <li>
            <p>Create a new repository for this project called <code>CryptoClustering</code>. <strong>Do not add this homework to an existing repository</strong>.</p>
        </li>
        <li>
            <p>Clone the new repository to your computer.</p>
        </li>
        <li>
            <p>Push your changes to GitHub.</p>
        </li>
    </ol>
    <h3>Files</h3>
    <p>Download the following files to help you get started:</p>
    <p><a href="https://static.bc-edx.com/data/dl-1-2/m19/lms/starter/Starter_Code.zip">Module 19 Challenge files</a></p>
    <h3>Instructions</h3>
    <ol>
        <li>
            <p>Rename the <code>Crypto_Clustering_starter_code.ipynb</code> file as <code>Crypto_Clustering.ipynb</code>.</p>
        </li>
        <li>
            <p>Load the <code>crypto_market_data.csv</code> into a DataFrame.</p>
        </li>
        <li>
            <p>Get the summary statistics and plot the data to see what the data looks like before proceeding.</p>
        </li>
    </ol>
    <h4>Prepare the Data</h4>
    <ul>
        <li>
            <p>Use the <code>StandardScaler()</code> module from <code>scikit-learn</code> to normalize the data from the CSV file.</p>
        </li>
        <li>
            <p>Create a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.</p>
            <ul>
                <li>
                    <p>The first five rows of the scaled DataFrame should appear as follows:</p>
                    <p><img src="https://static.bc-edx.com/data/dl-1-2/m19/lms/img/scaled_DataFrame.png" alt="The first five rows of the scaled DataFrame"></p>
                </li>
            </ul>
        </li>
    </ul>
    <h4>Find the Best Value for k Using the Original Scaled DataFrame</h4>
    <p>Use the elbow method to find the best value for <code>k</code> using the following steps:</p>
    <ul>
        <li>Create a list with the number of k values from 1 to 11.</li>
        <li>Create an empty list to store the inertia values.</li>
        <li>Create a <code>for</code> loop to compute the inertia with each possible value of <code>k</code>.</li>
        <li>Create a dictionary with the data to plot the elbow curve.</li>
        <li>Plot a line chart with all the inertia values computed with the different values of <code>k</code> to visually identify the optimal value for <code>k</code>.</li>
        <li>Answer the following question in your notebook: What is the best value for <code>k</code>?</li>
    </ul>
    <h4>Cluster Cryptocurrencies with K-means Using the Original Scaled Data</h4>
    <p>Use the following steps to cluster the cryptocurrencies for the best value for <code>k</code> on the original scaled data:</p>
    <ul>
        <li>Initialize the K-means model with the best value for <code>k</code>.</li>
        <li>Fit the K-means model using the original scaled DataFrame.</li>
        <li>Predict the clusters to group the cryptocurrencies using the original scaled DataFrame.</li>
        <li>Create a copy of the original data and add a new column with the predicted clusters.</li>
        <li>Create a scatter plot using hvPlot as follows:
            <ul>
                <li>Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".</li>
                <li>Color the graph points with the labels found using K-means.</li>
                <li>Add the "coin_id" column in the <code>hover_cols</code> parameter to identify the cryptocurrency represented by each data point.</li>
            </ul>
        </li>
    </ul>
    <h4>Optimize Clusters with Principal Component Analysis</h4>
    <ul>
        <li>
            <p>Using the original scaled DataFrame, perform a PCA and reduce the features to three principal components.</p>
        </li>
        <li>
            <p>Retrieve the explained variance to determine how much information can be attributed to each principal component and then answer the following question in your notebook:</p>
            <ul>
                <li>What is the total explained variance of the three principal components?</li>
            </ul>
        </li>
        <li>
            <p>Create a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.</p>
            <ul>
                <li>
                    <p>The first five rows of the PCA DataFrame should appear as follows:</p>
                    <p><img src="https://static.bc-edx.com/data/dl-1-2/m19/lms/img/PCA_DataFrame.png" alt="The first five rows of the PCA DataFrame"></p>
                </li>
            </ul>
        </li>
    </ul>
    <h4>Find the Best Value for k Using the PCA Data</h4>
    <p>Use the elbow method on the PCA data to find the best value for <code>k</code> using the following steps:</p>
    <ul>
        <li>Create a list with the number of k-values from 1 to 11.</li>
        <li>Create an empty list to store the inertia values.</li>
        <li>Create a <code>for</code> loop to compute the inertia with each possible value of <code>k</code>.</li>
        <li>Create a dictionary with the data to plot the Elbow curve.</li>
        <li>Plot a line chart with all the inertia values computed with the different values of <code>k</code> to visually identify the optimal value for <code>k</code>.</li>
        <li>Answer the following question in your notebook:
            <ul>
                <li>What is the best value for <code>k</code> when using the PCA data?</li>
                <li>Does it differ from the best k value found using the original data?</li>
            </ul>
        </li>
    </ul>
    <h4>Cluster Cryptocurrencies with K-means Using the PCA Data</h4>
    <p>Use the following steps to cluster the cryptocurrencies for the best value for <code>k</code> on the PCA data:</p>
    <ul>
        <li>Initialize the K-means model with the best value for <code>k</code>.</li>
        <li>Fit the K-means model using the PCA data.</li>
        <li>Predict the clusters to group the cryptocurrencies using the PCA data.</li>
        <li>Create a copy of the DataFrame with the PCA data and add a new column to store the predicted clusters.</li>
        <li>Create a scatter plot using hvPlot as follows:
            <ul>
                <li>Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".</li>
                <li>Color the graph points with the labels found using K-means.</li>
                <li>Add the "coin_id" column in the <code>hover_cols</code> parameter to identify the cryptocurrency represented by each data point.</li>
            </ul>
        </li>
        <li>Answer the following question:
            <ul>
                <li>What is the impact of using fewer features to cluster the data using K-Means?</li>
            </ul>
        </li>
    </ul>