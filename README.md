### BikeStore Project
## SQL / Excel / Tableau

![image](https://user-images.githubusercontent.com/107339963/235015896-ac5dab48-6a92-4a8c-9813-bceb57c5ae02.png)


Primero, debe descargar el siguiente archivo zip si no lo ha hecho:

https://www.sqlservertutorial.net/wp-content/uploads/SQL-Server-Sample-Database.zip


En segundo lugar, descomprima el archivo zip, verá tres archivos de script SQL:

 BikeStores Sample Database - create objects.sql – Este archivo es para crear objetos de base de datos, incluidos esquemas y tablas.
 BikeStores Sample Database - load data.sql – Este archivo es para insertar datos en las tablas
 BikeStores Sample Database - drop all objects.sql – Este archivo sirve para eliminar las tablas y sus esquemas de la base de datos de muestra. Es útil cuando desea actualizar la base de datos de ejemplo.

## Paso 1

Crear base de datos con nombre : BIKESTORES

## Paso 2

Seleccione la base de datos de muestra de BikeStores – crear objetos.sql archivo y habrá el archivo en SQL
Ejecutar la consulta.(tablas, esquemas)

## Paso 3 

Elija el archivo BikeStores Sample Database – load data.sql y haga clic en el botón Abrir.
Ejecutar la consulta.(datos)

# Listo a cargado la base de datos de ejemplo BikeStores en SQL Server.


## Codigo SQL:
use BikeStores
go

	SELECT 
		ord.order_id,
		CONCAT(cus.first_name, ' ' , cus.last_name) AS 'customers',
	 	cus.city,
	 	cus.state,
	 	ord.order_date,
	 	SUM(ite.quantity) AS 'total_units',
	 	SUM(ite.quantity * ite.list_price) AS 'revenue',
	 	pro.product_name,
	 	cat.category_name,
	 	sto.store_name,
	 	CONCAT(sta.first_name,' ',sta.last_name) AS 'sales_rep'
	FROM [sales].[orders] as ord
	JOIN [sales].[customers] as cus
	ON ord.customer_id = cus.customer_id
	JOIN [sales].[order_items] as ite
	ON ord.order_id = ite.order_id
	JOIN [production].[products] as pro
	ON ite.product_id = pro.product_id
	JOIN [production].[categories] as cat
	ON pro.category_id = cat.category_id
	JOIN [sales].[stores] as sto
	ON ord.store_id = sto.store_id
	JOIN [sales].[staffs] as sta
	ON ord.staff_id = sta.staff_id
	GROUP BY
	ord.order_id,
	CONCAT(cus.first_name,' ',cus.last_name),
	cus.city,
	cus.state,
	ord.order_date,
	pro.product_name,
	cat.category_name,
	sto.store_name,
	CONCAT(sta.first_name,' ',sta.last_name)
	

## Dashboard Tableau 
 https://public.tableau.com/app/profile/angelo.jeffrey.castillo.p.rez/viz/BikeStoreDashboard_16755725102730/BikeStore_Dashboard

<a href="https://www.instagram.com/angelocastilloperz/">
  <img align="left" alt="Abhishek's Instagram" width="22px" src="https://raw.githubusercontent.com/hussainweb/hussainweb/main/icons/instagram.png" />
</a>
<a href="https://twitter.com/AngeloCasell">
  <img align="left" alt="Abhishek Naidu | Twitter" width="22px" src="https://raw.githubusercontent.com/peterthehan/peterthehan/master/assets/twitter.svg" />
</a>
<a href="https://www.linkedin.com/in/castilloperz/">
  <img align="left" alt="Abhishek's LinkedIN" width="22px" src="https://raw.githubusercontent.com/peterthehan/peterthehan/master/assets/linkedin.svg" />
</a>
