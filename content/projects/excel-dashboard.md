---
date: 2021-01-10 05:20:35 +0300
draft: false
title: Sales Performance Dashboard – Excel
subtitle: Developed dynamic pivot-table dashboard to visualize revenue KPIs and regional performance.
tags: [Excel, Slicer, Pivot Table]
image: '/images/excel_dashboard.png'
demo_url: 'https://1drv.ms/x/c/1a9c56a123c62e62/Eb7j80heq6pPnN949qqj1sgBrKrC9KbOcDKn1ruumBJ3gw'
repo_url: 'https://github.com/Itsaakashgupta/Data-Analysis-Dashboard'
seo:
  page_description: 
  canonical_url: 
  featured_image: 
  author_twitter_handle: 
  open_graph_type:
  no_index: false
---
# Ankita-Store-Date-Analysis (Interactive Dashboard creation using MS Excel)

- Developed an interactive sales performance dashboard in Excel, incorporating pivot 
tables, slicers, and dynamic charts.  
- Visualized key performance indicators (KPIs), including total sales and regional 
performance metrics, enabling quick executive reporting and informed decision support.

## Project Objective
The Ankita store want to create an annual store report for 2024. So that, The owner of Ankita store can understand their customer purchase behaviour and buying habit and can grow their sales in 2025.

> **Download Worked File** - [***Click Here***](/uploads/store_analysis.xlsx)

<iframe id="excel-embed" width="100%" height="700" frameborder="0" scrolling="no"></iframe>
<div id="excel-fallback" style="font-size:14px;margin-top:8px;color:#666"></div>
<script>
  (function () {
    var isLocal = /^(localhost|127\.0\.0\.1)$/i.test(window.location.hostname);
    // Public URL where the site is deployed (ensure this file exists after deploy)
    var prodFileUrl = 'https://itsaakashgupta.github.io/uploads/store_analysis.xlsx';
    var fileUrl = isLocal ? prodFileUrl : (window.location.origin + '/uploads/store_analysis.xlsx');

    var src = 'https://view.officeapps.live.com/op/embed.aspx?src=' + encodeURIComponent(fileUrl) +
      '&wdAllowInteractivity=True&wdHideGridlines=True&wdHideHeaders=True&wdDownloadButton=True';

    var iframe = document.getElementById('excel-embed');
    if (iframe) iframe.src = src;

    // Helpful hint for local dev
    var hint = 'Note: Live Excel preview requires a publicly accessible file. On localhost this uses the deployed file: ' + prodFileUrl + ' .';
    var fb = document.getElementById('excel-fallback');
    if (fb) {
      fb.innerHTML = hint + ' If the preview fails, <a href="' + prodFileUrl + '" target="_blank" rel="noopener">open the workbook directly</a>.';
    }
  })();
</script>

## Process
  - Verify data for any missing values and anomalies, and sort out the same
  - Made sure data is consistent and clean with respect to data type, data format and values used.
  - Created pivot tables according to the question asked
  - Merge all pivot tables to a single dashboard to make it dynalmic and also apply the slicer

## Actionable insights
- Investigate the declining sales trend, considering factors like seasonality, competition, marketing effectiveness, and customer experience.
- Focus marketing efforts on the dominant female customer base.
- Optimize performance on key sales channels (Myntra, Amazon, Flipkart) and investigate the "Others" category.
- Analyze product category performance to inform inventory and marketing decisions.
- Investigate reasons for returns, refunds, and cancellations to improve processes and customer satisfaction.
- Leverage insights from top-performing states to enhance sales in other regions.