# `<z-dialog>`

Dialog element which supports `[data-source]` binding and `save` / `discard` event

- could open, close with save, close without save it
- could set label, content and footer button free
- could fire save or discard event and get content value easily at the same time

## Attributes

- `label`: dialog title
- `confirmlabel`: confirm button label in dialog footer
- `unconfirmlabel`: unconfirm button label in dialog footer

## Methods

- `load([value])`
- `confirm()`
- `unconfirm()`

## Events

- `save`
- `discard`

## Child Elements

- `[data-source]`: the element whose `value` will be communicated outside, both read and write

## Examples

```
<style>
  z-dialog {width: 320px;}
  z-dialog z-input-text {padding: 15px;}
</style>

<z-dialog id="z-dialog-test" label="Link URL" confirmlabel="Save" unconfirmlabel="Cancel">
  <z-input-text label="Please Input a URL:" data-source value="http://"></z-input>
</z-dialog>

<script>
  var dialog = document.querySelector('html /deep/ #z-dialog-test');

  dialog.load('http://www.google.com/');

  dialog.addEventListener('save', function (e) {
    // console.log('save', e.detail.value);
  });
  // dialog.confirm();

  dialog.addEventListener('discard', function (e) {
    // console.log('discard', e.detail.value);
  });
  // dialog.unconfirm();
</script>
```
