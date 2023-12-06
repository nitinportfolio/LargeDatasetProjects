Working with Large Datasets
Out of Core Machine Learning
1) Sub Sampling - Reducing the size of dataset either by reducing the number of rows or columns. Not a very goood approach as we will lose information.
2) Use Cloud computing - Rent higher RAM config. - Not good approach
3) Out of Core ML - It means working on the data that can't fir the computers RAM. Good approach.
How Out of Core ML Works - 
1. Streaming data - Get the stream of data in the batches from external source. For this we need data readers. Keras & pandas has inbuilt readers. We can even use Vaex library.
2. Extracting Features - 
3. Train Model - As we can't load the entire data into the RAM hence we can't train, so we use incremental learning. We train by fetching data in mini batches. Not all ML models can be
trained this way. Only those models that has partial_Fit parameter available, can be used. - SGD regresssor, Naive Bayes, Mini Bactch K means clustering.

Using VAEX Package to work with large datasets

Vaex is a python library for lazy Out-of-Core DataFrames (similar to Pandas), to visualize and explore big tabular datasets. It can calculate statistics such as mean, sum, count, standard deviation etc, on an N-dimensional grid up to a billion (
) objects/rows per second. Visualization is done using histograms, density plots and 3d volume rendering, allowing interactive exploration of big data. Vaex uses memory mapping, a zero memory copy policy, and lazy computations for best performance (no memory wasted).

# Its not bringing entire data to the memory but loading only the meta data.
df = vaex.open("./data/large_data.hdf5")


