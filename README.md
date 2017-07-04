# Datainsertion
Using Volley

This is a simple application build to insert data into remote database . 
This application runs on localhost and database is created on XAMPP server. 
The database name is user_db and the table name is user_info .
The table contains two column name(varchar(50)) and email(varchar(50)).
Inorder to insert into databse we have to write a php script and its name is update_info.php
 
 	 <?php
 	 $user_name=$_POST["name"];
 	 $user_pass=$_POST["email"];
 	 $user="root";
 	 $password="";
 	 $host="localhost";
  	$db_name="user_db";
 	 $con=mysqli_connect($host,$user,$password,$db_name);
 	 $sql="insert into user_info values('$user_name','$user_pass');";
 	 if(mysqli_query($con,$sql))
	  {
		  echo "Data insertion success";
 	 }
 	 else
	  {
		  echo"Error while insertion";
 	 }
 	 mysqli_close($con);
  	?>
  
Add a dependency in gradle for using volley library 

	compile 'com.mcxiaoke.volley:library:1.0.19'

Than we create a stringRequest in java file.
Inorder  to send data along with onResponse() and onErrorResponse() we have to overrie another method getParams() .
This will return string value pair in type of Hashmap.
Than by using the map variable use the method put 
	
	params.put("name",name);
  	params.put("email",email);

Inorder to add this string request to requestQueue there are several methods but we will add it to requestQueue using a new class Singelton.
And than add the stringRequest to requestQueue.
