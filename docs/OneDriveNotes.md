### 备份文件夹

对于OneDrive而言，默认的[同步文件夹](https://www.zhihu.com/search?q=同步文件夹&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra={"sourceType"%3A"answer"%2C"sourceId"%3A1876681114})共有**四个**，分别包括：

1. “**桌面**”“**文档**”与“**图片**”文件夹。

2. **自动同步的OneDrive文件夹**，默认路径为“C:\用户\[用户名]\OneDrive”。

3. 其中，**自动同步的OneDrive文件夹**的实际位置取决于初次配置OneDrive帐号时用户的选择。

   一般地，将需要同步的文件或文件夹放入上述四个文件夹内，即可实现本地与[OneDrive云端](https://onedrive.live.com/)的文件同步。如果我们需要同步电脑中其它位置的文件或文件夹，可以将他们直接复制粘贴到上述四个文件夹内，但比较麻烦。因此，我们可以借助`mklink`命令实现。

   例如，如果我们需要将原本不在OneDrive同步文件夹内的“G:\我的图片”文件夹及其中内容放入OneDrive。

   首先，摁下`Windows`键，输入`cmd`，选择“命令提示符”，并选择“以管理员身份运行”。

   在打开的界面中，输入：

   ```text
   mklink /d "C:\用户[用户名]\OneDrive\aaa\我的图片" "G:\我的图片"
   ```

   其中，第一个引号内部前半部分为OneDrive所在的位置，第二个引号内部为需要同步的文件夹路径与名称。**注意：**第一个引号中的路径，`\我的图片`是onedrive自动创建的，不需要提前创建；但`\我的图片`所在的目录（`C:\用户[用户名]\OneDrive\aaa`）必须存在。

   

参考资料：[Onedrive 如何同步一个文件夹? - 知乎 (zhihu.com)](https://www.zhihu.com/question/265950919)