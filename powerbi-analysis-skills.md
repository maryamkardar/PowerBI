Upwork website: a great platform for freelancers and businesses to connect and collaborate on projects.
Microsoft PL_300 certification <br>
We are not able to manipulate data source, we just read it.<br>
<br>
**Power BI Development LifeCycle:** 
Data Discovery ---> Data Transformation ---> Data Modeling ---> Data Visualization ---> Data Distribution
Power BI Desktop ---> stages 1 to 4
Power BI Report Server ---> stage 5 "For those who use servers"<br>
Power BI Service ---> stage 5 "For those who use cloud services"<br>
<br>
GIGO: Garbage In ---> Garbage Out<br>
<br>
There is no any DAX functions for cumulative sales for 6 months.<br>
<br>
1. Month-to-Date (MTD) Sales<br>
Use TOTALMTD to calculate cumulative sales from the start of the month to the current date:<br>
MTD_Sales = TOTALMTD(<br>
    SUM(SalesData[SalesAmount]),<br>
    SalesData[Date]<br>
)<br>
<br>
2. Quarter-to-Date (QTD) Sales<br>
Use TOTALQTD to compute sales from the beginning of the quarter:<br>
QTD_Sales = TOTALQTD(<br>
    SUM(SalesData[SalesAmount]),<br>
    SalesData[Date]<br>
)<br>
<br>
3. Year-to-Date (YTD) Sales<br>
Use TOTALYTD to sum all sales from the start of the year:<br>
YTD_Sales = TOTALYTD(<br>
    SUM(SalesData[SalesAmount]),<br>
    SalesData[Date]<br>
)<br>
<br>
4. Custom Rolling Cumulative Sales<br
                                      
If you need rolling cumulative sales over a custom period (e.g., last 12 months), use:<br>
Rolling_12M_Sales = <br>
CALCULATE(<br>
    SUM(SalesData[SalesAmount]),<br>
    DATESINPERIOD(SalesData[Date], LASTDATE(SalesData[Date]), -12, MONTH)<br>
)<br>
<br>
5. Running Total Across All Dates<br>
If you want a running total without resetting per month, quarter, or year:<br>
Running_Total = <br>
CALCULATE(<br>
    SUM(SalesData[SalesAmount]),<br>
    FILTER(<br>
        ALL(SalesData[Date]),<br>
        SalesData[Date] <= MAX(SalesData[Date])<br>
    )<br>
)<br>
<br>
**ALL and FILTER functions return a table**<br>
<br>
If a calculation result is specific, you should import it as an entery data in PBI and don't use DAX Functions.<br> 
IF data is static and isnot dynamic.<br>

