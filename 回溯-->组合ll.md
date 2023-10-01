**组合总和II**

**我今天二叉树刷完之后我再回头想去刷回溯复习一波虽然做出来了但是我是凭肌肉记忆写的，复盘一下组合问题。**
```javaScript
var combine = function(n, k) {
let path = []
function dfs(start,res){
    if(res.length==k){
        path.push([...res])
        return
    }
    for(let i=start;i<=n;i++){
        res.push(i)
        dfs(i+1,res)
        res.pop()
    }
    return res
}
dfs(1,[])
return path
};
```
我一直在纠结要不要在dfs函数里面加i+1参数因为我忘记这个参数在去重上起到什么作用了很困惑，吃完饭了好好研究一下。
但一想又明白了dfs(i+1,res)一直在一个答案进行回溯，如果[1,2]遍历完了就pop()i+1起的是一个答案内部的去重。如果画出二叉树的话就是深度遍历的时候去重得到一条路径的答案。

回溯的题型主要有：
组合 🐶
排序
子集
