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
>这个环境变量用于选择graphcap供ctrans使用。

>默认值：无

>如果没有设置这个环境变量，则必须使用command line flags

**NCARG_GKS_OUTPUT（关键字 gks_output）**
>用于指示ncgm workstation输出的元文件(metafile)的默认文件名。

>默认值：gmeta

**NCARG_GKS_PSOUTPUT（无关键字）**
>用于指示PS workstation输出的PostScript文件的默认文件名。Stdout也适用。

>默认值：gmeta1.ps

**NCARG_USRRESFILE（关键字 usrresfile）**
>用于定义用户的HLU资源文件，这种文件用于定义所有HLU程序的资源。

>默认值：~/.hluresfile<br/>
>**备注：**这个默认值可在编译时配置，所以系统管理员可以更改它。

**NCARG_ROOT（关键字 root）**
>用于指示NCL安装的根目录。如果正确设置后，与该变量关联的别的环境变量也会定义好。

>默认值：/usr/local<br/>
>**备注：**这个默认值可在编译时配置，所以系统管理员可以更改它。

**NCARG_BIN（关键字 bin）**
>用于指示NCL的bin目录位置。

>默认值：$(NCARG_ROOT)/bin

**NCARG_MAN（关键字 man）**
>用于指示NCL的man页面位置。

>默认值：$(NCARG_ROOT)/man

**NCARG_INCLUDE（关键字 include）**
>用于指示NCL包含文件的位置。

>默认值：$(NCARG_ROOT)/include

**NCARG_LIB（关键字 lib）**
>用于指示NCL库的位置。

>默认值：$(NCARG_ROOT)/lib

**NCARG_NCARG（关键字 ncarg）**
>用于指示附加文件的位置，比如数据库，资源文件等等。

>默认值：$(NCARG_LIB)/ncarg

**NCARG_COLORMAP_PATH（无关键字）**
>用于设置color tables位置的路径列表，包括NCL标准色标。这个变量可以设置自定义的color tables目录，参见[创建自定义色标](http://www.ncl.ucar.edu/Document/Graphics/create_color_table.shtml)

>默认值：$(NCARG_NCARG)/colormaps

**NCARG_COLORMAPS（关键字 colormaps）**
>用于指示NCL色标的默认位置。

>默认值：$(NCARG_NCARG)/colormaps

**NCARG_RANGS（关键字 rangs）**
>用于指示RANGS/GSHHS数据库的位置。这个数据库体积大，并没有默认包含在NCL中。

>默认值：$(NCARG_NCARG)/rangs

**NCARG_CONFIG（关键字 config）**
>用于指示NCL配置文件的位置。（只有从源码安装的NCL才有这些配置文件，二进制安装的NCL不需要）

>默认值：$(NCARG_NCARG)/config

**NCARG_DATABASE（关键字 database）**
>用于指示NCL数据库文件的位置(map databases etc)

>默认值：$(NCARG_NCARG)/database

**NCARG_DATA（关键字 data）**
>用于指示用于NCL和HLU示例的数据文件位置。

>默认值：$(NCARG_NCARG)/data

**NCARG_FONTCAPS（关键字 fontcaps）**
>用于指示fontcaps的位置。

>默认值：$(NCARG_NCARG)/fontcaps

**NCARG_GRAPHCAPS（关键字 graphcaps）**
>用于指示graphcaps的位置。

>默认值：$(NCARG_NCARG)/graphcaps

**NCARG_HLUEX（关键字 hluex）**
>用于指示Fortran HLU示例的位置。

>默认值：$(NCARG_NCARG)/hluex

**NCARG_NCLEX（关键字 nclex）**
>用于指示NCL示例的位置。

>默认值：$(NCARG_NCARG)/nclex

**NCARG_RESFILES（关键字 resfiles）**
>用于指示NCL和HLU示例的资源文件位置。

>默认值：$(NCARG_NCARG)/resfiles

**NCARG_EXAMPLES（关键字 examples）**
>用于指示ow-level示例的位置（可能不包含在二进制的NCL中）。

>默认值：$(NCARG_NCARG)/examples

**NCARG_TESTS（关键字 tests）**
>用于指示low-level测试示例的位置（可能不包含在二进制的NCL中）。

>默认值：$(NCARG_NCARG)/tests

**NCARG_TUTORIAL（关键字 tutorial）**
>用于指示low-level教程的位置（可能不包含在二进制的NCL中）。

>默认值：$(NCARG_NCARG)/tutorial

**NCARG_XAPP（关键字 xapp）**
>用于指示NCL X程序资源文件的位置。

>默认值：$(NCARG_NCARG)/xapp

**NCARG_SYSRESFILE（关键字 sysresfile）**
>用于指示系统资源文件的位置。

>默认值：$(NCARG_NCARG)/sysresfile

**NCARG_SYSAPPRES（关键字 sysappres）**
>用于指示NCL Application资源文件的位置。

>默认值：$(NCARG_NCARG)/sysappres

**NCL_DEF_LIB_DIR（无关键字）**
>如果设置这个环境变量为一个合法的路径名，NCL将搜索该目录下的动态共享对象（*.so文件）供NCL动态加载。这些*.so文件是运行[WRAPIT](http://www.ncl.ucar.edu/Document/Tools/WRAPIT.shtml)或"wrapit77"创建的。

>也就是说，为了调用新函数或进程，当用["external"](http://www.ncl.ucar.edu/Document/Manuals/Ref_Manual/NclStatements.shtml#external)声明载入*.so文件时，无需预设SO_NAME::给被引用的函数或进程。NCL会尝试载入被NCL_DEF_LIB_DIR指定的目录下的所有文件，如果有文件不是共享对象，你会收到警告信息。

>更多信息，参见[WRAPIT](http://www.ncl.ucar.edu/Document/Tools/WRAPIT.shtml#SetEnvironmentVariable)文档的[用环境变量加载共享对象](http://www.ncl.ucar.edu/Document/Tools/WRAPIT.shtml#SetEnvironmentVariable)章节，或参考手册的[载入默认脚本和共享库](http://www.ncl.ucar.edu/Document/Tools/WRAPIT.shtml#SetEnvironmentVariable)章节。

>默认值：无

**NCL_DEF_SCRIPTS_DIR（无关键字）**
>如果设置这个环境变量为一个合法的路径名，NCL将尝试加载该目录下所有".ncl"后缀的文件，就像用["load"](http://www.ncl.ucar.edu/Document/Manuals/Ref_Manual/NclStatements.shtml#load)声明调用一样。

>这些文件按UNIX目录结构顺序加载，所以如果某个文件依赖于另外一个还未载入的文件，你就会遇到问题。

>参考手册["载入默认脚本和共享库"](http://www.ncl.ucar.edu/Document/Manuals/Ref_Manual/NclFormatSupport.shtml#GRIB1-user-defined-parameter-tables)章节获取更多信息。

>默认值：无

**NCL_GRIB_PTABLE_PATH（无关键字）**
>NCL GRIB参数表文件是定义一个或多个参数表供NCL读取GRIB文件的文本文件。设置该变量为参数表文件路径，NCL在第一次打开GRIB文件时会分析、合并参数表文件。并且，NCL_GRIB_PTABLE_PATH环境变量也可以设置为一个目录，则该目录下的所有'.gtb'后缀文件会被当做参数表文件打开。

>参考手册["用户定义的GRIB1参数表"](http://www.ncl.ucar.edu/Document/Manuals/Ref_Manual/NclFormatSupport.shtml#GRIB1-user-defined-parameter-tables)章节获取更多信息。

>默认值：无

**NCL_NO_SYSTEM_PAGER（无关键字）**
>默认的，[system](http://www.ncl.ucar.edu/Document/Functions/Built-in/system.shtml)为方便用户阅读而分页显示内容。该变量的值用于设定分页，如果没设置，则用“更多”做分页。如果不想用”更多“做分页，设定该环境变量可关闭分页。

>默认值：无

**NIO_GRIB2_CODETABLES（关键字　grib2_codetables）**
>用于指示[GRIB2代码表](http://www.ncl.ucar.edu/Document/Manuals/Ref_Manual/NclFormatSupport.shtml)位置。

>默认值：$NCARG_ROOT/lib/ncarg/grib2_codetables

**PAGER（无关键字）**
>这不是特定的NCL环境变量，而是用于别的UNIX程序。在NCL中，这个参数定义[print](http://www.ncl.ucar.edu/Document/Functions/Built-in/print.shtml)和[system](http://www.ncl.ucar.edu/Document/Functions/Built-in/system.shtml)的输出如何分页。

>默认值： "more"

**PSADILOOKUP_PATH（无关键字）**
>用于指示"psadilookup.dat"文件的位置，该文件被用于[rip_cape_3d](http://www.ncl.ucar.edu/Document/Functions/Built-in/rip_cape_3d.shtml)和[rip_cape_2d](http://www.ncl.ucar.edu/Document/Functions/Built-in/rip_cape_2d.shtml)函数。

>默认值：$NCARG_ROOT/lib/ncarg/data/asc

**TMPDIR（关键字　tmp）**
>用于指示NCL临时文件目录。

>默认值：/tmp
>>**备注：**这个默认值可在编译时配置，所以系统管理员可以更改它。
