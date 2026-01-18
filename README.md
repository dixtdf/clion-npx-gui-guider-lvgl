# clion-npx-gui-guider-lvgl
Clion导入恩智浦(NXP)Gui Guider项目

```shell
# 1.将本项目的 CMakeLists.txt 放到Gui Guider创建项目的父级文件夹,并修改LVGL_ROOT_DIR和GG_PROJECT_DIR的目录,例如我这边是nxp-demo那么就改成nxp-demo,你要做的是把nxp-demo改成你自己目录。
# 2.打开Gui Guider项目至少构建一次
# 3.在Clion打开Gui Guider项目的父级文件夹
PS C:\Users\Administrator\Desktop\my-lvgl> ls
目录: C:\Users\Administrator\Desktop\my-lvgl
Mode                 LastWriteTime         Length Name                                                                                                            
----                 -------------         ------ ----                                                                                                            
d-----         2026/1/18     13:01                .idea                                                                                                           
d-----         2026/1/18     13:01                cmake-build-debug-mingw                                                                                         
d-----         2026/1/18     12:48                nxp-demo                                                                                                         
-a----         2026/1/18     13:01           1280 CMakeLists.txt
```  
# 吐槽
NXP Gui Guider自己的代码编辑器实在是太难用了，几乎没有代码检查和代码提示，就连代码整理也没有，对于刚入门c/c++的新手非常不友好。</br>
官方似乎没有优化的意思。</br>
但是还是非常感谢NXP Gui Guider提供了好用的GUI LVGL设计器！</br>
