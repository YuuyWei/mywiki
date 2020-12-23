# Tries(单词查找树)
:algorithm:java:

基于通用算法的符号表性能止步于对数数量级。不过对于给定Alphabet的字符串而言，我们有着更为高效的查找算法——单词查找树。

## 接口
以字符串作为符号表的键的接口。
```
public interface StringST<Value> {
    void put(String key, Value value); // 将键值对存入符号表

    Value get(String key); // 获取键为key的值

    void delete(String key); // 删除键为key的值

    default boolean contains(String key) // 返回是否存在键key
    {
        return get(key) != null;
    }

    default boolean isEmpty() // 判断符号表是否为空
    {
        return size()==0;
    }

    int size(); // 返回表中键值对数量

    Iterable<String> keys(); // 符号表中的所有键

    String longestPrefixOf(String s); // s中前缀最长的键

    Iterable<String> keysWithPrefix(String s); // 所有以s为前缀的键

    Iterable<String> keysThatMatch(String s); // 所有和s匹配的键（其中.匹配任意字符）
}
```
该接口和一般的符号表的不同之处在于：
- 将泛型的Key类型换成了具体的String类型。
- 添加了三个方法：
    - `longestPrefixOf()`
    - `keysWithPrefix()`
    - `keysThatMatch()`
