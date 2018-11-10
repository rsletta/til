# SAP GUI for Java - Connection strings

The way you define a new SAP Connection in SAP GUI For Java differs slightly from SAP GUI For Windows. Let’s assume that you have the following connection information:

Address: 10.1.3.40
System No: 02
In SAP GUI For Java, you need to get to the “Advanced” tab, click “Expert mode” and enter the following connection string:

```
conn=/H/10.1.3.40/S/3202
```

Obviously, the address goes between /H/ and /S/ and the system number goes to the end of the string. If your system ID is 00, you need to enter 3200. If your system ID is 07, you need to enter 3207. In our case, your system ID is 02 so you need to enter 3202.