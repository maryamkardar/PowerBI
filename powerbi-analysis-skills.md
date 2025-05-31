Upwork website: a great platform for freelancers and businesses to connect and collaborate on projects.<br>
Microsoft PL_300 certification <br>
We are not able to manipulate data source, we just read it.<br>
<br>
**Power BI Development LifeCycle:** <br> 
Data Discovery ---> Data Transformation ---> Data Modeling ---> Data Visualization ---> Data Distribution<br>
Power BI Desktop ---> stages 1 to 4<br>
Power BI Report Server ---> stage 5 "For those who use servers"<br>
Power BI Service ---> stage 5 "For those who use cloud services"<br>

GIGO: Garbage In ---> Garbage Out

There is no any DAX functions for cumulative sales for 6 months.

1. Month-to-Date (MTD) Sales
Use TOTALMTD to calculate cumulative sales from the start of the month to the current date:
MTD_Sales = TOTALMTD(
    SUM(SalesData[SalesAmount]),
    SalesData[Date]
)


