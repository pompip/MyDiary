### 大坑

> 1. 如果在Fragment中使用onContextMenu，或者是使用onOptionsItemSelected，一定要注意每个Menu Item的ID
> 2. 同一个Activity下的所有Fragment，这两个方法都会调用，所以注意ID要分开。