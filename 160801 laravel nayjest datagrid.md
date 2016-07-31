#Datagrid with Nayjest Grid in Laravel

Wanna use datagrid with your Laravel application? I suggest this one: Nayjest Datagrid. How?

1. Play with composer like this:

```
composer require "nayjest/grids"
```

2. Modify your Laravel application, on `config/app.php`

On provider section:

```
'Nayjest\Grids\ServiceProvider',
```

If you use laravel 5^, as I use too, you should need laravel collective component. So,  `config/app'php` becomes like below:

```
'Nayjest\Grids\ServiceProvider',
'Collective\Html\HtmlServiceProvider',
```

On Alias section:

```
  'Form'  => 'Illuminate\Html\FormFacade',
  'HTML'  => 'Collective\Html\HtmlFacade',
  'Grids'     => 'Nayjest\Grids\Grids',
```

3. This is the example that you should place in your any view file...

```
$cfg = [
    'src' => 'App\User',
    'columns' => [
            'id',
            'name',
            'email',
            'country'
    ]
];
echo Grids::make($cfg);
```

Hope it helpful...

See directly from the source:
- https://github.com/Nayjest/Grids
- 

If you want some alternatives, you may try these:
- https://github.com/zofe/rapyd-laravel (also includes widgets datatable, form, datatree, data filter, etc)
- https://github.com/zofe/datagrid
