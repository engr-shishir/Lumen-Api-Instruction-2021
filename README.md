# Lumen Rest Api
 Lumen Rest Api 2021
 <br><br><br>


>## Representaional State Transfer
+ Rest Api works with` Client Server`
+ Rest Api `Stateless`.Because `Api Script` can't store any sata
+ `Cacheable`. That menans when client get data from api script, he can store some data
+ Uniform interace


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




>## 04 <===============> Pass Parameters From Router to Controller
+ web.php
```php
$router->get('/test/{name}', [DemoController::class, 'Test');
```
+ DemoController.php
```php
class DemoController extends Controller {
  public function Test($name)
  {
    return "My name is".$name;
  }
}

```
<br><br>




>## 05 <===============> Api Response
+ web.php
```php
$router->get('/test/{name}', [DemoController::class, 'Test');
$router->get('/test', [DemoController::class, 'Json');
$router->get('/redirect', [DemoController::class, 'redirect');
$router->get('/download', [DemoController::class, 'download');
```
+ Response Area `body,header`
+ Response Type `simple string,json,xml,download,redirect`
+ DemoController.php
```php

// String Response with header & body
  public function Test($name)
  {
    return response($name)
           ->header('name',$name)
           ->header('age',28);
  }



// json response in body from array
  //simple array
  public function Json()
  {
    $myArray = array('cat','bat','net');
    return response()->json($myArray);
  }
  //multidimentional array
  public function Json()
  {
    $myArray = array
    (
      array('Volvo',200),
      array('BMW',500),
      array('Sab',700)
    )
    return response()->json($myArray);
  }
  //asociative array
  public function Json()
  {
    $myArray = array('cat'=>'30','bat'=>'35','net'=>'38');
    return response()->json($myArray);
  }




// Response Redirect
public function redirect()
{
  return redirect('/');
}



// Response Download
public function download()
{
  $path = 'demo.pdf';
  return response()->download($path);
}

```
<br><br>







>## 06 <===============> Sending And Catching
+ Client Send <---> Api Catch Data <---> Api Slice Data <---> Database
+ way of sending and catching `url,header,json data using body`
+ Request Class
+ web.php
```php
$router->post('/catch', [DemoController::class, 'catch');
```
+ DemoController.php
```php
use Illuminate\Http\Request;

public function catch(Request $request)
{
  return $request; // this way api only can access parameter and body data

  return $request->header(); // this way api can access header data

  return $request->header('key'); // this way api can access header specific value according to key
}

```
<br><br>
