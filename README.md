# Prediction Engine for Stock Market

## I. Introduction

The stock market, also known as the equity market or share market, is a platform where buyers and sellers engage in economic transactions of stocks or shares, representing claims of ownership on businesses. Examples include shares of private companies sold through equity crowdfunding platforms. Stock exchanges list various security types, such as common equity shares, corporate bonds, and convertible bonds.

This project aims to predict near real-time stock values for various commodities, helping investors make informed decisions about their future investments. Stock market prediction involves determining the future value of a company's stock or other financial instruments traded on an exchange. Accurately predicting a stock's future price can lead to significant profits for investors.

Some theories suggest that stock prices reflect all available information, making any changes unpredictable without new information. However, others believe that future price information can be obtained using various methods and technologies. The values predicted in this project are approximate and intended to assist in decision-making.

The R language is used to predict stock values in this project. R provides powerful statistical tools for linear and nonlinear modeling, time series analysis, classification, clustering, and more. R's advantage lies in its ability to produce high-quality plots and statistical analysis.

### Methodologies Used:

1. **Time Series of Data Using Trendlines**
2. **Correlation of Data**
3. **Probable Cause Analysis**
4. **Headroom Analysis**

## II. Methodologies

### 1.1 Trendlines

Trendlines show variations over time and help visualize progress. The `trend.line()` function in R is used to plot different models:

- **Linear (lin2P):** y=ax+b
    
    y=ax+by = ax + b
    
- **Quadratic (lin3P):** y=ax2+bx+c
    
    y=ax2+bx+cy = ax^2 + bx + c
    
- **Logarithmic (log2P):** y=aln(x)+b
    
    y=aln⁡(x)+by = a \ln(x) + b
    
- **Exponential (exp3P):** y=aexp(bx)+c
    
    y=aexp⁡(bx)+cy = a \exp(bx) + c
    
- **Power (power3P):** y=axb+c
    
    y=axb+cy = ax^b + c
    

The `trend.line()` function is used to track stock prices graphically. A sample code snippet is:

```r
rCopy code
trend.line(x, y, type = "linear", plot = TRUE)

```

Here, `type` can be linear, quadratic, exponential, etc., depending on the model.

### 1.2 Functions

User-defined functions are a powerful feature in R. Functions are used in this project to calculate future stock values. Examples include:

```r
rCopy code
sum <- function(a, o) {
    trendline(a, o, model = "line2P", plot = TRUE)
}

predi <- function(u) {
    h <- u$Year
    av <- u$Avg
    relation <- lm(av ~ h)
    print(relation)
    print(summary(relation))
    newdata <- data.frame(h = 2018)
    result <- predict(relation, newdata)
    print(result)
}

```

### 1.3 Correlations in Functions

Stock values are correlated to analyze and audit the data. The `cor()` function is used to produce correlations, and the `cov()` function is used for covariances. An example:

```r
rCopy code
cor(x, use = "everything", method = "pearson")

```

## III. Reading the Data

Data is read from various sources, such as Excel files or text files, into R using methods like `read.csv()` for CSV files and `read.delim()` for text files. The prediction engine is designed to predict stock prices for a specified year based on the input data. Examples of reading data:

```r
rCopy code
x <- read.csv("gold.csv", header = TRUE)
y <- read.csv("crudeoil.csv", header = TRUE)
z <- read.csv("silver.csv", header = TRUE)
m <- read.csv("aluminium.csv", header = TRUE)

```

## IV. Results

The trendlines for stock commodities corresponding to the years are shown below:

- **Fig.1:** Aluminium
- **Fig.2:** Crude Oil
- **Fig.3:** Gold
- **Fig.4:** Silver

## V. Interpretation

The graphs indicate that stock prices peaked in 2012. These trends help guide the decision-making process, allowing investors to make more informed choices based on historical data and predicted trends.
