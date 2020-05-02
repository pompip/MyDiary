# java反射

## static值
> Modifier 获取修饰

```
 void printStaticFiledValue(Class<?> clazz) {
		Field[] fields = clazz.getFields();
		for(Field f:fields) {
			f.setAccessible(true);
			try {
				if(Modifier.isStatic(f.getModifiers())) {
					Object value = f.get(clazz);
					log("chong----------key:"+f.getName()+"  value:"+value);
				}
			
			} catch (Exception e) {
				e.printStackTrace();
			} 
		}
	}
```