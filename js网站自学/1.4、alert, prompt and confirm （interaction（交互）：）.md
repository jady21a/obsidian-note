`alert`

显示信息。

`prompt`

显示信息要求用户输入文本。点击确定返回文本，点击取消或按下 Esc 键返回 `null`。

`confirm`

显示信息等待用户点击确定或取消。点击确定返回 `true`，点击取消或按下 Esc 键返回 `false`。

## [prompt](https://javascript.info/alert-prompt-confirm#prompt) （提示）
```
result = prompt (title, [default]); 
```
![[Pasted image 20220316174813.png]]
## [confirm](https://zh.javascript.info/alert-prompt-confirm#confirm)
```
result = confirm (question);
```
`confirm` 函数显示一个带有 `question` 以及确定和取消两个按钮的模态窗口。

点击确定返回 `true`，点击取消返回 `false`。