
With turnover as(SELECT firstName, lastname, orderdate, month(orders.orderDate)as mois, year(orders.orderDate)as année,sum(orderdetails.quantityordered*priceeach)as ca, row_number() over (partition by mois, année) as row_num
From customers
Join employees On employees.employeeNumber=customers.salesRepEmployeeNumber
Join orders Using (customerNumber)
join orderdetails using(ordernumber)
Group by firstname, lastname, année, mois
Order by année, mois,ca desc)
select firstName, lastname, année, mois, ca
from turnover
where row_num <3;
