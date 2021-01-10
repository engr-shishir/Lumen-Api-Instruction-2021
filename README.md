# Lumen Rest Api
 Lumen Rest Api 2021
 <br><br><br>



>## 01 
## Create Lumen New Project
  `composer create-project --prefer-dist laravel/lumen blog`
## Run Project
  `php -S localhost:8000 -t public`
<br><br>



>## 02 <===============> Basic Routing
+ routes/web.php
```php

// get Meathoad
$router->get('/get', function(){
  return "I Come From Api get Meathoad";
});

// post Meathoad
$router->post('/post', function(){
  return "I Come From Api post Meathoad";
});

// put Meathoad
$router->put('/put', function(){
  return "I Come From Api put Meathoad";
});

// delete Meathoad
$router->delete('/delete', function(){
  return "I Come From Api delete Meathoad";
});


Now if we want to tes this methoad we should use poastman application. Browser can check only get meathoad
```
<br><br>



>## 03 <===============> Route Parameters
<=====>  Required Parameters
<=====>  Optional Parameters
+ routes/web.php
```php

// Pass Required One Parameters
$router->post('/name/{name}', function($name){
  return $name;
});

// Pass Required Maultipple Parameters
$router->post('/name/{nameValue}/age/{ageValue}', function($nameValue,$ageValue){
  return $nameValue.$ageValue;
});


// Pass Optional Parameters
$router->post('/name/{nameValue}[/{ageValue}]', function($nameValue,$ageValue=null){
  return $nameValue.$ageValue;
});
```
<br><br>


