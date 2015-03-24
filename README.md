# dialog

对话框

* 可以打开、保存并关闭、不保存并关闭对话框
* 可以随意添加内容
* 可以在打开和保存时和内容的数据进行交流

该对话框会：

* 提供label, confirmlabel, unconfirmlabel三个外设特性
* 自动绑定标签里带有[data-source]的第一个元素的value值
* 提供load(value), confirm(), unconfirm()三种方法
* 同时提供save, discard两个事件可供监听

## Example

<z-dialog label="添加网址" confirmlabel="保存" unconfirmlabel="关闭">
  请输入你想访问的网址：<br>
  <input type="url" data-source value="http://">
</z-dialog>

<script>
  var dialog = document.querySelector('z-dialog');

  dialog.load('http://www.google.com/');

  dialog.addEventListener('save', function (e) {...});
  // dialog.confirm();

  dialog.addEventListener('discard', function (e) {...});
  // dialog.unconfirm();
</script>
