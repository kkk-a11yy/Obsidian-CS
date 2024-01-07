# Java List --remove(int index)与remove(Object o)方法的区别
---

remove(int index)：该方法删除位于index结点处的元素

remove(Object o)：删除特定Object元素

在大多数情况下，这两种方法的使用并不会存在歧义。

但是当我们将List的泛型参数设置为Integer时，我们只能使用前一种方式删除元素，也即是按结点位置的方法删除元素。因为无论传入的参数是int 类型还是Integer类型，都只会调用remove(int index)方法，而不会调用remove(Object o)方法。

