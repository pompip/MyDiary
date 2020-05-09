# java反射

## static值

> Modifier 获取修饰

```java
 void printStaticFiledValue(Class<?> clazz) {
		Field[] fields = clazz.getFields();
		for(Field f:fields) {
			f.setAccessible(true);
			try {
				if(Modifier.isStatic(f.getModifiers())) {
					Object value = f.get(clazz);
				}
			} catch (Exception e) {
				e.printStackTrace();
			} 
		}
	}
```
