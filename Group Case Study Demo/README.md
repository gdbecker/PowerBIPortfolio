# Group Case Study Demo

Earlier on in my time at Elliott Davis my manager was looking for a dashboard pack we could showcase in a variety of settings to get the word out on the Data & Analytics service line at our firm, as well as provide a starter point of conversation for clients interested in adding on analytics for their engagements. A couple of colleagues and I first worked on our own files and individual dummy data models across different industries - and then from which I combined everything into one file we could post online to our Power BI Service Workspace. As with other demos/proposals I worked on this one was a great showcase of what my team and I could do as well as the significant functionality within Power BI.

### [Live Demo](https://app.powerbi.com/view?r=eyJrIjoiODQ1MjE2MjUtZTk3MS00MGVmLTk5MGYtZmUxMDc4NmY5NjI2IiwidCI6ImY3N2E4MGM5LTY5MTAtNGJkYy1iNjFiLTgxNzA2NmQ1NmI0NiIsImMiOjJ9)

!["Report"](./Group%20Case%20Study%20Demo.jpg)

## Project Details
- [Group Case Study Demo](#group-case-study-demo)
    - [Live Demo](#live-demo)
  - [Project Details](#project-details)
  - [Details](#details)
  - [By the Numbers](#by-the-numbers)
  - [Tools Used](#tools-used)
  - [Data Engineering Pipeline](#data-engineering-pipeline)
  - [Data Model](#data-model)
  - [What I learned](#what-i-learned)
  - [Useful Resources](#useful-resources)

## Details

The guidelines on this one were loose for the purpose of being able to show anything we had learned in the app up to this point, with the goal of showcasing Power BI's capabilities as best as possible. My manager wanted each of us to choose a different industry to form dummy data in and then create visuals from, so we picked construction, retail and e-commerce as our focal points. Each file had a different style, so when I combined them altogether I established a theme to match Elliott Davis's branding as close as possible. It was a great challenge to start figuring out the Advanced Editor in the Power Query backend in order to copy the data pipelines and sources from other files into one, as well as making sure the three data models were copied exactly.

Files included for view in this project:
- [`Group Case Study Demo.pdf`](./Group%20Case%20Study%20Demo.pdf): All of our separate demos put into one file

## By the Numbers

- < 1 month of development time
- 3 colleagues collaborated with
- 20 report pages
- 1 data source
- 14 queries connected to data source

## Tools Used

- Excel
- Power BI
  - DAX
  - Power Query
- SharePoint (data source)

## Data Engineering Pipeline

!["Pipeline"](./Group%20Case%20Study%20Demo%20Pipeline.png)

## Data Model

!["Data Model"](./Group%20Case%20Study%20Demo%20Data%20Model.JPG)

## What I learned

Below are some code snippets from my colleagues and I from this project:

```DAX
Cumulative Sales Forecast = 
    CALCULATE( 'Sales Forecasting'[Sales Forecast], 
        FILTER(ALLSELECTED('Date Table'[Date]),
            'Date Table'[Date] <= MAX('Date Table'[Date])
        )
    )
```

```DAX
Total Sales = 
    CALCULATE(
        SUM(Lokad_SalesOrders[PO Amount]),
        ALLEXCEPT('Date Table','Date Table'[Date])
    )
```

```DAX
Cumulative Inventory Forecast = 
    CALCULATE( 'Inventory Sales based on Sales Orders'[Inventory Qty Forecast], 
        FILTER(ALLSELECTED('Date Table'[Date]),
            'Date Table'[Date] <= MAX('Date Table'[Date])
        )
    )
```

## Useful Resources

- [Power BI: Advanced Editor](https://www.myonlinetraininghub.com/tips-for-using-the-power-query-advanced-editor) - I've discovered the Advanced Editor view of the backend queries to be a huge help in not just changing a query data source, but also adding in custom transformation steps 