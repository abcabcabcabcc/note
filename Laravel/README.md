
### eloquent 批量保存

```php
    //data内每个需要保存的数据属性必须一致,否则会报错
    $data = [
        [...],
        [...],
    ];

    Model::insert($data);
```

### eloquent model attribute

```php
namespace App\Model;
use Illuminate\Database\Eloquent\Model;
use Illuminate\Database\Eloquent\SoftDeletes;

class Flight extends Model{
    use SoftDeletes; //软删除. 

    //制定模型链接数据库使用的连接名称
    protected $connection = 'test';

    //eloquent 表名默认为模型类的复数形式 name+s,自定义表名可以设置该变量
    protected $table = 'foo'; 

    //是否允许该模型自动维护时间戳
    protected $timestamps = false;

    //timestamps 为true时,自定义数据被 创建/更新时间维护的表字段名称
    const CREATED_AT = 'creation_date';
    const UPDATED_AT = 'last_update';

    //允许被批量赋值的字段
    protected $fillable = [
        'fieled1',
        'fieled2',
    ];

    //与 fillable 相反, 不允许被批量赋值的字段属性
    protected $guarded = [];

    //json返回时,附加的字段
    protected $appends = [
        'foo1',
        'foo2',
    ];
}
````

### eloquent find

```php
    $user =User::find($id); //select * from users where primary_key=$id
    //increment
    $user->login_count++; $user->save();
    //or
    $user->increment('login_count');

```

### eloquent first

```php
    $model = Model::where('name','foo')->get();
    //返回 collection对象 判断model 是否存在
    if(!$model->isEmpty()){
        $first_model = $model->first();
    }

    //写法二:
    $model = Model::where('column', 'foo')->first(); //return model or null

    //写法三:
    try{
        $model = Model::where('column', 'foo')->firstOrFail();
    }catch(ModelNotFoundException){
        //not exist
    }

    //写法四:
    $model = Model::where('column','foo');
    if($model->exists()){
        $model = $model->first();
    }
```