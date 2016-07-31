#Use Powerful Input Class

Feel boring when you use variables like this `$_GET['datapenting']` or some similar with that? In Laravel, we can use a class with powerful ability: Input.

This class is actually named `Illuminate\Support\Facades\Input`. We can call this name with only `Input` after we create alias for this class. So, how to?

1. Modify file `config/app.php`, find the section alias.

```
'Input' => Illuminate\Support\Facades\Input::class,
```

2. Then you can use for get input from HTTP request, such as GET or POST. This is very useful in any view files.

As an example, here I use in a view file:

```
echo Input::get('page');
//that similar with this
echo $_GET['page'];  //--> but this will return error if there are no URL parameter with 'page', so the code will be like this

if(isset($_GET['page'])
  echo $_GET['page']);
  
```

In another example, I use it for rendering my table....

```
{!! mydata->appends(['parent'=>Input::get('parent')])->render() !!}
```

How about using Input in Laravel 5.2^? You just need not modify anything, because the class Input has been replaced with class Request.

So where ever you need to input something instead of using
```
Input:: 
```
use
```
Request::
```
And if you get error something about 'should not use statically' just add this at the top of your file
```
use Request;
```
If you already have this line:

```
use Illuminate\Http\Request;
```
delete it because you can't have two classes with the same name in one file

Thanks for your attention. You're very kind. 

Source: http://stackoverflow.com/questions/31696679/laravel-5-class-input-not-found
