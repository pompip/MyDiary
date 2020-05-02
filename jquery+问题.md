# jquery 问题
## $("#aaa")[0].innerHTML=data；代码中为什么一定要加[0]才能正常显示？
> $('#aaa')取得的是一个jQuery对象。而innerHTML是一个DOM属性。
所以你要把jQuery对象转为DOM才行。
而数组下标可以转成DOM对象。
jQuert对象有特有的方法，无需转为DOM，例如
$('#aaa').html(data) 