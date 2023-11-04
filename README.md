### Original Paper

[GCNET: Graph-based prediction of stock price movement using graph convolutional network - ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0952197622004420)

### Dataset Source

https://github.com/ut-kdd/GCNET-Dataset

### Graph Example

![](/Users/rebeccameow/Library/Application Support/typora-user-images/截屏2023-11-05 02.03.12.png)

### Experimental Results

The paper used the daily stock market data of the 100 largest Nasdaq stocks by market capitalization from 2011 to 2020, and after screening the data quality, 81 stocks were retained. The stock relationship graph was updated every 30 days (at the beginning of each month). The QDA in the process of generating the stock relationship graph was divided into training and test sets in an 8:2 ratio, while the PLD was divided into a 6:1 ratio. The test set included the 10 most recent trading days before the target date, and the coefficient used for adjusting the accuracy score was 0.8 with a weight index decrease. The percentage of target date labeled nodes was 20%.

The training of GCN was implemented using the dgl library based on PyTorch. The input and output dimensions of each layer of GCN and other parameters such as learning rate (set to 0.01) were set according to general experience. Each graph was iterated for 30 epochs.

Tests were conducted on all trading days between September 30, 2020 and December 30, 2020, and each experiment was repeated independently for 10 times a day. The average accuracy obtained was 56.07, which was close to the original paper's result of 56.71.