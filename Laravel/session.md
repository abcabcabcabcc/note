session 有效期设置

```php
// config/session.php

'lifetime' => env('SESSION_LIFETIME', 120),  // 可以在.env文件中配置
'expire_on_close' => false,  // 改为true 表示浏览器关闭的时候就失效
```
