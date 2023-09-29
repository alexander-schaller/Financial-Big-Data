*******************************************************************************
*                         SUPPORTING DATASET FOR PAPER:                       *
*   MEASURING SYNCHRONIZATION AND ANTICIPATION BETWEEN INDIVIDUAL INVESTORS   *
*                         FROM THEIR DAILY PERFORMANCE                        *
*******************************************************************************


The data stored here is used as a support of the paper "Measuring
synchronization and anticipation between individual investors from their
daily performance" where a measure based on Mutual Information and
Transfer of Entropy is used in order to map investors' behaviour and which
ones are following same behavioural patterns.

The study linked to this data is published on pre-print Arxiv.org
 with the following citation:


    Mario Gutiérrez-Roig, Javier Borge-Holthoeffer, Alex Arenas and
    Josep Perelló. Measuring synchronization and anticipation between
    individual investors from their daily performance (2018)


For any question or comment please contact any author of the paper.

DATA PROTECTION DISCLAIMER

In order to satisfy privacy issues, all personal data about the investors
is been anonymized and de-identified in agreement with the Spanish Law for
Personal Data Protection and the institutional review board and data protection
commissioner of the Universitat de Barcelona.


DATASET CONTENT

-- Investors position timeline --

This dataset is generated after processing and filtering a larger raw dataset
that reports trading activity of 29,930 clients being small size
non-professional traders that invest their own savings. All their decisions
are genuinely human and not taken by any kind of algorithmic trading robot,
although its is completely possible that some of them are influenced by some
kind of advice. Investors traded over 120 different assets in the BME Spanish
stock exchange from 01/01/2000 until 12/31/2008 (1 969 trading days). In total,
the raw dataset contains 3 303 695 transactions, where each record includes the
ID of the client, the ID of associated manager from the investment firm,
the date of the transaction, the price of the asset and the number of shares
being sold or bought.

The filtered version of the dataset is constrained to the performance of the
most active investors (daily position balance, number of shares bought minus
number shares sold, is greater than zero for at least 50 days ) and for the
assets that contain at least 20 investors that fulfill with the previous
requirement. By descending order in size, these are: Telefonica (TEF), from
communications sector, with 291 most active investors accounting for 98 046
transactions; Santander (SAN), from finance sector, with 154 most active
investors accounting for 47 842 transactions; BBVA (BBVA), from finance sector,
with 76 most active investors accounting for 29, 314 transactions; Endesa (ELE),
from utilities sector, with 61 most active investors accounting for 25 735
transactions; Ezentis (EZE), from industrial sector, with 58 most active
investors accounting for 18 488 transactions; Zeltia (ZEL), from health care
sector, with 54 active investors accounting for 16 435 transactions;
Repsol (REP), from energy sector, with 43 active investors accounting for
16 066 transactions; Gas Natural (GAS), from utilities sector, with 24 active
investors accounting for 20 097 transactions. In summary, this dataset contains
the the performance of 417 different individuals accounting for 272 023
transactions over 8 assets.

-- Assets Price timeline --

Contains the historical time series of the 8 assets studied.

Data source: Yahoo Finance

-- Networks (Bonferroni and FDR)--

Data of the networks built by processing the investors performance using Mutual
Information and Transfer of Entropy techniques as described in the abovementioned
paper. The suffixes for the netowrk files refer to the false positive adjustment
method applied (Bonferroni or FDR) in order to consider whether links between
investors are significant or not.   

DATASET STRUCTURE

The dataset contains 24 CSV files plus this README.text file. There are 8 assets
and 3 files per asset:

    - Investors: Individual portfolio (number of shares hold) of the investors
      over time:
        1) investor id
        2) date
        3) position (number of shares)


    - Prices: Historical prices of all assets.
        1) price record id
		2) date
		3) closing price
		4) open price
		5) daily maximum
		6) daily minimum
		7) total daily volume

    - Network (Bonferroni and FDR): Edge list between investors (nodes) of
      the network. For each edge some extra inforation is collected regarding
      the performance of both investors and features of the overlapping period:
		1) ticker (asset)
		2) investor i node id
		3) investor j node id
        4) investor i id 
		5) investor j id
		6) investor i manager id
		7) investor j manager id
		8) investor i Mutual Information between position and price
		9) investor j Mutual Information between position and price
		10) investor i Transfer of Entropy between position and price
		11) investor j Transfer of Entropy between position and price
		12) first day of overlapping interval between node i and j
		13) first day of overlapping interval between node i and j
		14) number of trading days in the ij overlapping interval
		15) number investor i active days (position balance not 0)
		16) number investor j active days (position balance not 0)
		17) Mutual Information between investor i and investor j
			(link weight in Synchronization Network)
		18) Transfer of Entropy between investor i and investor j
	    (link weight in Anticipation Network)

