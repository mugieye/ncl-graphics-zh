**NCL环境变量**

要运行NCL，只有一个环境变量需要设置，就是NCARG_ROOT，设置为NCL的安装目录（不是包含ncl命令的bin目录）。NCL通过NCARG_ROOT环境变量定位资源文件，比如地图数据、色标、字体和示例程序。所有用户在使用NCL前都要设置该变量，或是帮你安装NCL的人要告诉你该变量的位置。

高级用户可以创建自己的color maps或者移动部分NCL组件到NCARG_ROOT之外的目录，这种情况需要用额外的环境变量来指定这些文件的新位置。

比如，你要[创建自己的color tables](http://www.ncl.ucar.edu/Document/Graphics/create_color_table.shtml)并放在某处，可以用NCARG_COLORMAP_PATH这个环境变量指定这些色表的路径，但是仍然要保持NCL标准色表的路径。

另一个例子是，如果你要安装[ RANGS/GSHHS](http://www.ncl.ucar.edu/Document/Graphics/rangs.shtml)高分辨率的地图数据库，默认的路径是$NCARG_ROOT/lib/ncarg/database/rangs。如果是放置在别的地方，可以用NCARG_RANGS环境变量指明新位置的路径。

所有的NCL环境变量会在下面列出，对于其中的一些环境变量，你可以在命令行下运行ncargpath程序加关键字作为参数取得该环境变量的默认值，或者在NCL脚本里调用[ncargpath](http://www.ncl.ucar.edu/Document/Functions/Built-in/ncargpath.shtml)函数，传关键字为参数获取默认值。

以下是所有的NCL环境变量，以及是否能通过ncargpath关键字获取默认值。

**DISPLAY（无关键字）**
>这不是特定的NCL环境变量，而是用于X11窗口程序。当你用X11窗口显示图形，或是用[ictrans](http://www.ncl.ucar.edu/Document/Tools/ctrans.shtml)，[ctrans](http://www.ncl.ucar.edu/Document/Tools/ictrans.shtml)或[idt](http://www.ncl.ucar.edu/Document/Tools/idt.shtml)浏览NCGM文件的时候，需要指定该变量。
>>这个变量需要设置为显示图形的主机ip地址或是机器名，比如"localhost:13.0"。如果你不是运行在远程主机，可以设置为":0.0"

>>默认值：视操作系统不同，这个值可能已经设置。

**GRAPHCAP（关键字graphcap)**
