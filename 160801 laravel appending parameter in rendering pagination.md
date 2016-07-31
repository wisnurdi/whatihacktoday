#Appending Parameter in Rendering Pagination with Laravel

You may add to the query string of pagination links using the appends method. For example, to append &sort=votes to each pagination link, you should make the following call to appends:

```
{!! $users->appends(['sort' => 'votes'])->render() !!}
```

If you wish to append a "hash fragment" to the paginator's URLs, you may use the fragment method. For example, to append #foo to the end of each pagination link, make the following call to the fragment method:
```
{!! $users->fragment('foo')->render() !!}
```
[Laravel 5.1 Pagination: Displaying Results In A view Documentation](http://laravel.com/docs/5.1/pagination#displaying-results-in-a-view)

In your case it will be something like this:

```
{!! $users->appends(['search' => $searchTerm])->render() !!}
```

Also, you can check the lesson [Crazy Simple Pagination](https://laracasts.com/lessons/crazy-simple-pagination), it's in Laravel 4 but the idea is the same.

Source: https://laracasts.com/discuss/channels/laravel/appending-url-param-for-paging-and-searching
