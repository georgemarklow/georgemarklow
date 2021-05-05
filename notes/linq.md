# LINQ

## Operations

### Filtering

```csharp
var col2 = Orders.Where(o => o.CustomerID == 84);
```
<br/>
### Return Anonymous Type

```csharp
var col2 = orders.Select(o => new
{
    OrderID = o.OrderID,
    Cost = o.Cost
});
 ```
 <br/>
 
 ### Ordering
 
```csharp
var col2 = orders.OrderBy(o => o.Cost);
```

```csharp
var col4 = orders.OrderByDescending(o => o.Cost);
```
 
```csharp
var col6 = orders.OrderBy(o => o.CustomerID).
    ThenByDescending(o => o.Cost);
```
<br/>

### Joining

```csharp
var col2 = customers.Join(orders,
    c => c.CustomerID,o => o.CustomerID,
    (c, o) => new
    {
        c.CustomerID,
        c.Name,
        o.OrderID,
        o.Cost
    }
 );
```

### Grouping

```csharp
var OrderCounts1 = orders.GroupBy(
    o => o.CustomerID).
    Select(g => new
    {
        CustomerID = g.Key
        TotalOrders = g.Count()
    }
);
```


## Conversions
