# Superagent的用法

![superaget](http://visionmedia.github.io/superagent/)

Super Agent is light-weight progressive ajax API crafted for flexibility, readability, and a low learning curve after being frustrated with many of the existing request APIs。
Superagent是一个轻量的渐进的Ajax API，与现有的其他许多request API相比，它灵活性强，可读性高，学习难度低。

```
request
    .post('/api/pet')
    .send({name:'Manny', specise: 'cat'})
    .set('X-API-Key','foobar')
    .set('Accept','application/json')
    .end(function(err, res) {
        if(err || !res.ok){
            alert('Oh no! error!');
        }else{
            alert('yeah! Get' + JSON.stringify(res.body));
        }
        });
```

基本的请求
可以调用`request`对象中适当的方法初始化一个请求，然后使用`end()`发送请求。
```
request
    .get('/search')
    .end(function(err, res){

        })
```
或者以字符串方式也可以
```
request('GET', '/search').end(callback);
```

设置请求头
设置请求头只需简单地调用`set()`方法,其参数可以是键值对，也可以一个对象。
```
request.
get('/search')
.set('API-Key','footbar')
.set('Accept', 'appliction/json')
.end(callback);
```

```
request
.get('/search')
.set({'"API-Key': 'foobar', Accept: "appliction/json"})
.end(callback);
```
