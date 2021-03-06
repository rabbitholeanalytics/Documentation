---
title:  Indicator Data Seems Wrong
summary: "Make sure you compare with the actual source of the raw data and research the raw data before reporting an issue."
sidebar: suite_sidebar
permalink: suite-troubleshooting-indicator-data-seems-wrong.html
---

You may be comparing one of Superalgos' indicators with indicators produced by other sources like TradingView, Sierra Chart, or any other provider. You may have found some differences, probably minor, in some of the indicator properties for certain candles, or maybe even throughout the data set.

One of the most likely reasons for these mostly minor discrepancies is that the raw data exchanges provide is not always consistent. For example, occasionally a one-minute candle may be missing in the data set. Or some candles may not start exactly at the zero-seconds mark.

Our OHLCVs sensor bot fetching data from exchanges works recursively to ensure no data is missed, however, we have no control over the data the exchange delivers at any point.

Furthermore, there is no information as to how third-parties obtain the data they serve, or what measures they may be taking when they detect inconsistencies in the datasets.

It is reasonable to conclude that minor differences with third-party providers are to be expected.

If you worry about the quality of the data of any of the indicators running on Superalgos, the first thing to do is to compare the data with the source, not a third-party&mdash;that is, the actual exchange.

If you find inconsistencies in some of our data with the data provided by the exchange, then, the second step to investigate what the issue may be is to compare the raw data, that is, one-minute candles. If you find differences in the one-minute candles provided by Superalgos and the one-minute candles provided by the exchange, then we may have a case in which the sensor bot requires some debugging to find out what the problem may be. In such a case, please [open an issue](suite-how-to-report-an-issue.html) pointing us to the specific candles that you found to be wrong.

If one-minute candles seem to be correct and there is an inconsistency in the data provided by a Superalgos indicator, first, make sure that candles are correct throughout the period required to calculate the indicator. For example, in the case of a 50-periods moving average, you need to check the last 50 candles from the point in which you find a discrepancy in the indicator. If such is the case, please open an issue indicating the process you went through to determine that there is something wrong with the said indicator and point us to the specific point in time where the indicator is wrong.