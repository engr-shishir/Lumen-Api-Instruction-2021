# Lumen Api
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



