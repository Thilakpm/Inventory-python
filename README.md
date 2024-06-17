# Inventory-python
I am working on a test project. It's a Inventory/Sales system  based on python/django/vs code 

I have two templates 1. view_sales.html


<!DOCTYPE html>
<html>
<head>

        
    <title>Sales</title>
    <title>Product Total_price</title>

    
    {% load static %}
    <link rel="stylesheet" type="text/css" href="{% static 'sales/styles.css' %}">
</head>

</head>
<body>

    <header>
        <img src="{% static 'images/TrialImg.png' %}" alt="Logo">
    </header>

    <h1>Sales</h1>
    <table border="1">
        <tr>
            <th>Product</th>
            <th>Date</th> 
            <th>Amount</th>                     
            <th>Quantity Sold</th>           
            <th>Total Price</th>
        </tr>
        {% for sale in sales %}
        <tr>
            <td>{{ sale.product.product_name }}</td>
            <td>{{ sale.date }}</td>                      
            <td>{{ sale.amount }}</td>
            <td>{{ sale.quantity_sold}}</td>
            <td>{{ sale.total_price }}</td>
        </tr>

        
            

        {% endfor %}
    </table>
    <h2>Total Sales: {{ total_sales }}</h2>    
    
    <ul>

        <li><a href="{% url 'add_sale' %}">Add Sale</a> </li>
        <li><a href="{% url 'total_sales' %}">show the Total Sale </a></li>

    </ul>       

           
</body>
</html>


************Output of the above file******************




Sales
Product	Date	Amount	Quantity Sold	Total Price
Laptop	May 24, 2024	599.00	-6	-3594.00
Laptop	May 17, 2024	599.00	5	2995.00
Laptop	May 17, 2024	599.00	3	1797.00
Laptop	May 9, 2024	599.00	2	1198.00
Laptop	May 7, 2024	599.00	4	2396.00
Laptop	May 5, 2024	599.00	2	1198.00
Laptop	April 17, 2024	799.00	2	1598.00
Laptop	March 16, 2024	599.00	2	1198.00
Laptop	March 16, 2024	599.00	5	2995.00
Laptop	March 11, 2024	599.00	2	1198.00
Total Sales: 6190
Add Sale ( this is a http)
show the Total Sale ( this is a http)


2. total_sales.html

<!DOCTYPE html>
<html>
<head>
    <title>Total Sales</title>
</head>
<body>
    <h1>Total Sales</h1>
    <p>{{ total_sales }}</p>
</body>
</html>


******Output of the above *******

Total Sales
12979.00


My question is : how do I merge these two outputs and display in one web page ????
