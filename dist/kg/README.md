最新版本&详细说明参见https://github.com/grapheco/InteractiveGraph

- [EnhancedInteractiveGraph](#enhancedinteractivegraph)
  - [<a name='ContributingtoInteractiveGraph'></a>改进内容(Contributing to InteractiveGraph)](#改进内容contributing-to-interactivegraph)


# EnhancedInteractiveGraph


[在线示例Demo](http://blog.zhimind.com/kg.html)
1. 读取 json 文件(见 kg.json) 或 csv文件（用@ 分隔， 见 kg.csv)
2. 关键词(keywords)属性查找过滤
3. 点击节点显示信息框（和原版一致），  改进点， 长按 ctrl 再点击节点， 会显示另一个信息框
4. link/video_link 属性， 可以显示外链 进行点击跳转

NOTE:

1. CTRL 要长按
2. 上传文件后， 才能根据关键词属性进行查找过滤——因为我实在改不动作者近10万行的代码， 所以初始时的 keyword 搜索框是没用的。
   
 
## <a name='ContributingtoInteractiveGraph'></a>改进内容(Contributing to InteractiveGraph)

1. Add a CmpBoxCtrl (see src/main/typescript/CmpBoxCtrl.ts), compare two nodes' information(but need mouse left-click with long pressing 'ctrl' for 1\2 seconds). 增加了一个对比信息框， 可以对比两个节点的信息， 不过因为对JS事件不太熟悉， 需要按 Ctrl 键较长时间（1、2秒）
2. Add the APIs of loadGsonString/loadGsonObj. 增加了 loadGsonString\loadGsonObj 接口
3. Supporting to upload a CSV/JSON file to render the graph. 在2的基础上，可以上传csv/json文件，直接绘图。
4. 因为实在是不熟悉JS， 调试找不到， 事件很难改， supporting to filter nodes with the property "keywords", 只能保存一个json字符串，转成json对象，再在所有节点的属性keywords中查找， 不包含关键词的节点不显示
   