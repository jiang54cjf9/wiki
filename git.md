当 sourcetree 进行交互式变基时卡死

使用命令行输入

git commit --amend

后会弹出一个文本编辑器，最上方是提交内容，然后再输入

git rebase --continue

进行确定

或者在卡死的时候点开 vscode，之后会弹出一个确认窗口，点击提交按钮后在 vscode 中的终端输入上面两行指令

更改完成后需要重启 SourceTree，不要点击 sourceTree 中的取消按钮，那样会直接将刚才的操作复原

