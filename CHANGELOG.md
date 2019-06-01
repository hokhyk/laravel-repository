更新记录
=======

2019-05-27
----------

- change: 基础类 Repository 修改
    - change: create、update、delete 不允许继承修改
    - change: Repository 方法命名规范，保持和laravel 一致, 这一点待定
        - 查询单个 first
        - 查询多个 get
        - 删除多个 同名方法 
    - update: delete 和 update 方法支持数组表达式查询
    
        ```php
        
            // 删除写法可以同查询方法一致
            $this->repository->delete([
                'username:like'    => 'username',
                'created_time:gte' => '2019-05-27 00:00:00',
            ]);
      
            // 修改方法可以同查询方法一致
            $this->repository->update([
                'username:like'    => 'username',
                'created_time:gte' => '2019-05-27 00:00:00',
            ], [
                  'status' => 1,
                  'type'   => 2,
            ])
            
        ``` 