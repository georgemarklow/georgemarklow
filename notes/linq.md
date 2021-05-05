# LINQ

## Filtering

```csharp
var col2 = Orders.Where(o => o.CustomerID == 84);
```

## Return Anonymous Type

```csharp
var col2 = orders.Select(o => new
{
    OrderID = o.OrderID,
    Cost = o.Cost
});
 ```
 
## Ordering
 
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

## Joining

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

## Grouping

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

## Paging (using Skip & Take)
```csharp
var col2 = orders
    .Where(o => o.CustomerID == 84)
    .Take(3);
```

```csharp
var col3 = (from o in orders
    where o.CustomerID == 84
    orderby o.Cost
    select o)
    .Skip(2).Take(2);
```

## Element Operators (Single, Last, First, ElementAt, Defaults)

```csharp
var cust1 = customers
    .Single(c => c.CustomerID == 84);
```

```csharp
var cust1 = customers
    .SingleOrDefault(c => c.CustomerID == 84);
```

```csharp
var cust1 = customers
    .Where(c => c.CustomerID == 85)
    .DefaultIfEmpty(new Customer())
    .Single();
```

```csharp
var cust5 = orders
    .Where(o => o.CustomerID == 84)
    .OrderBy(o => o.Cost).Last();
```

```csharp
var j = customers
    .Where(c => c.CustomerID == 85)
    .Select(o => o.CustomerID).SingleOrDefault();
```

## ToArray
```csharp
string[] names = (from c in customers select c.Name).ToArray();
```

## ToDictionary
```csharp
Dictionary<int, Customer> col = customers.ToDictionary(c => c.CustomerID);
Dictionary<string, double> customerOrdersWithMaxCost = (from oc in
(from o in orders
join c in customers on o.CustomerID equals c.CustomerID
select new { c.Name, o.Cost })
group oc by oc.Name into g
 select g).ToDictionary(g => g.Key, g => g.Max(oc => oc.Cost));
```
## ToList
```csharp
List<Order> ordersOver10 = (from o in orders
where o.Cost > 10
 orderby o.Cost).ToList();
```

## ToLookup
```csharp
ILookup<int, string> customerLookup =
 customers.ToLookup(c => c.CustomerID, c => c.Name);
```
