# Helpers
> you have to extend Activity to use this helpers

### Usage
```java
...
import com.framedroid.framework.Activity;

public class YourActivity extends Activity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Log.i("my screen width", String.valueOf(screen().width()));
    }
}
```

## ScreenHelper screen()

* `int width()`
* `int height()`
* `int halfWidth()`
* `int halfHeight()`


## TimeHelper time()

* `long diff()`
* `String diffFormat()`
* `Calendar toCalendar()`
* `void setFormat()`
* `String print()`
```java
Calendar calendar = Calendar.getInstance();

// print data in "yyyy-MM-dd" format i.e. 2017-03-23
Log.i("time format 1", time().print(calendar, "yyyy-MM-dd"));

// print data in default format i.e. 2017-03-23 17:55:31
Log.i("time format 2", time().print(calendar, "yyyy-MM-dd"));
```


## JsonHelper json()

Usage

```java
json().build(
    new JsonHelper.PreJson("id", 1234),
    new JsonHelper.PreJson("name", "Some name"),
    new JsonHelper.PreJson("price", 12.34),
    new JsonHelper.PreJson("anotherJson", json().build(
        new JsonHelper.PreJson("desc", "test")
    ))
);
```

Above code will produce json like:
```json
{
   "id":1234,
   "name":"Some name",
   "price":12.34,
   "anotherJson":{
      "desc":"test"
   }
}
```
