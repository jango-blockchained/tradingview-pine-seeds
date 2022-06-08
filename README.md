[guide_data]: /guide/data.md
[guide_repo]: /guide/repo.md 
[guide_ui]: /guide/ui.md
[ui_chart]: /images/ui_chart.png
[ui_details]: /images/ui_details.png
[ui_search]: /images/ui_search.png
[ui_pine]: /images/ui_pine.png
[pine_script_docs]: https://www.tradingview.com/pine-script-docs/en/v5/Introduction.html
[solution_eod]: https://www.tradingview.com/support/solutions/43000474958-i-see-only-eod-data-for-dxy-symbol-and-no-real-time/

# Pine Seeds documentation

## Overview

__Pine Seeds__ is a service for working with your data on the [TradingView](https://tradingview.com) platform.

This service allows you:

- connect your series data to TradingView
- visualize it in the TradingView UI
- use it to create indicators

Use [TradingView](https://tradingview.com) as your __frontend__ and use GitHub repository as your __backend__. 

Keep in mind that such data has limitations (we call them [EOD][solution_eod] data):

- the data can only be updated a few times a day
- only the daily resolution is available
- the number of data elements (symbols) is limited
- such data cannot be found with Symbol Search box

> __Note__
> 
> Read [5-minute tutorial](tutorial.md) to start right now

Setting up the service include of several steps.

1. [data preparation][guide_data]
1. setting up [repository][guide_repo]
1. manipulating data in the [TradingView UI][guide_ui]

A detailed description of the service can be found in the other sections.

### [Data structure][guide_data]

Data storage form, data structure, fields descriptions, fields types, data validation conditions.

### [GitHub settings][guide_repo]

Account and repository settings, GitHub actions workflow, repositories organization, external data connection.

### [TradingView UI][guide_ui]

Quick guide for TradingView user using custom data series.

## TradingView UI

There are several tools for working with your data here.

### Chart

This is the main data visualization tool. There are 12 types of charts, a lot of additional indicators, viewing historical data for any period.

![Chart][ui_chart]

### Details

Additional information about the symbol: name, source, current value, change per day.

![Details][ui_details]

### Symbol Search

A search box for the symbol. Enter the full name (`GROUP:SYMBOLNAME`) to see it on __Chart__.

![Symbol Search][ui_search]

### Pine Editor

Built-in TradingView [language][pine_script_docs]. 
A couple lines of code are enough to access the data. This is a flexible and convenient tool for displaying data on the __Chart__.

![Pine Editor][ui_pine]

## GitHub repository

__GitHub__ is your backend. This is where you upload the data. Here you update them.
We will prepare a repository for you. You will fork it.
You upload data to your fork.

GitHub-actions are already set up. They regularly check the data and create a __Pull Request__ to our repository.
See the results of the tests in the action's log.

## Data

You updload the data files to the repository. 

You can do it manually. Or, if you want, connect the storage in which they are collected from another source and converted into our format. 
This way require an additional repository.

The data is stored in two directories.

* `data/your_repo directory` — place CSV data files here. One file for one character. Add a row with data values for every day.
* `symbol_info` directory — place JSON file with a description of all symbols here. Add description for every CSV to this file.

> __Note__
> 
> For further information check out the [Frequently asked questions section](/faq.md)
