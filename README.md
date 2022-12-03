# consumption-profile-analysis
consumption profile analysis

- The course participants will receive a database with information on a **number of sales of products** from a (fictitious) company and customers. 
- They must analyze the dataset using cloud technologies designed for processing large volumes of data 
    - to simulate the division and management of the dataset and perform the necessary analysis.


- The company's objective, with new brands, is to specialize the stores in their customers, 
    - they will only have products that interest them, 
        - increasing sales and reducing expenses with transport and inventory. 
- However, dividing a company into several brands can be a costly process to manage the brand, advertising and employees are also specialized and therefore more costly.


# Questions to answer:

- How many brands should the company be divided into and why?
- What percentage of customers will be under the banner of each brand?
- What is the purchasing profile of each brand's customers?

These answers have been answered in the EDA (`consumption-profile-analysis/notebooks/eda.ipynb`).

# Which technologies should we use?
- Our customers data can be saved as a parquet in a `AWS S3` bucket, for example.
- For data processing: we can use `EMR` but it is not included in free tier, so we didn't use it directly here. Instead, we ran our data processing on a small volume using `Spark` on a free trial `t2.micro` instance, for example.
- For the EDA: we can deploy a container in `Kubernetes` with 6 CPUs and 128 GB for example. So we can train our `Kmean` on large volumes of data. But if the volume is too big, we should run `Kmean` on a representative sample of our data, so that it can fit in 128 GB memory.
