**.hluresfile**

[".hluresfile"][http://www.ncl.ucar.edu/Document/Graphics/hluresfile]文件用于改变NCL图表的默认设置，比如：

* 默认色标
* X11窗口的默认大小 (512 x 512)
* PNG图片的默认大小 (1024 x 1024)

[查看[这里](#jump)关于NCL V6.1.0版本（2012 10月发布）图表默认设置的变更]。

要创建hluresfile文件，查看[示例][hlfile]，重命名为".hluresfile"，编辑文件内容设置想要的效果，然后把该文件放到home目录。

如果有什么原因你不想放到home目录，可以放到任何目录，然后设置环境变量NCARG_USRRESFILE的值为该文件的绝对路径（包含文件名）。

以下是示例的".hluresfile"文件内容，可以按你想要的效果修改：

```
!=========================================
! This is a sample .hluresfile. It should
! go in your home directory.
!
! Comments for ".res" files are preceded by a "!".
! Remember quotations are not used in .res files.

! White background/black foreground, these are the default in V6.1.0
*wkForegroundColor  : (/0.,0.,0./)
*wkBackgroundColor  : (/1.,1.,1./)

! Have a favorite colormap that you use for everything? You can
! make it your default here (note the name is NOT in quotes).
!
! In Version 6.1.0, the default is "ncl_default":
! http://www.ncl.ucar.edu/Document/Graphics/ColorTables/ncl_default.shtml
!
! For all available color maps, see 
! http://www.ncl.ucar.edu/Document/Graphics/color_table_gallery.shtml
*wkColorMap         : BlueWhiteOrangeRed

! Font - this is the default in V6.1.0. 
! Use times-roman to get the pre-V6.1.0 default.
*Font           : helvetica 

! Function code - this is the default in V6.1.0. 
! Use ':' to get the pre-V6.1.0 default.
*TextFuncCode               : ~     
 
! Make default X11 window larger (the default is 512x512)
!*windowWorkstationClass*wkWidth  : 1000
!*windowWorkstationClass*wkHeight : 1000

! Make default PNG window larger (the default is 1024x1024)
!*imageWorkstationClass*wkWidth   : 2500
!*imageWorkstationClass*wkHeight  : 2500

! Note, if you just set wkWidth/wkHeight, this will affect both
! X11 window AND PNG image size
!*wkWidth   : 1500
!*wkHeight  : 1500

! Increase the default (16mb) contour memory.
! The default is 100000000.
! For example, if you have gridded data that
! is larger than 500 x 500, you may need this.
! *wsMaximumSize: 300000000
!==========================================
```

### <V6.1.0 id="jump"></V6.1.0>

### **NCL V6.1.0 图表默认设置变更**

在NCL 6.1.0版本中，图表的默认设置有一些改动。

在NCL 6.0.0及早期版本中，如下设置有效：

* [black background, white foreground][http://www.ncl.ucar.edu/Document/Graphics/Images/blackwhite.png]
* ["times-roman"][http://www.ncl.ucar.edu/Document/Graphics/Images/font0.png]字体
* [32-color][http://www.ncl.ucar.edu/Document/Graphics/ColorTables/default.shtml]色标
* 冒号(':')用于[function code][http://www.ncl.ucar.edu/Document/Graphics/function_code.shtml]

在NCL 6.1.0及后续版本中，如下设置有效：

* [white background, black foreground][http://www.ncl.ucar.edu/Document/Graphics/Images/whiteblack.png]
* ["helvetica"][http://www.ncl.ucar.edu/Document/Graphics/Images/font21.png]字体
* [256-color][http://www.ncl.ucar.edu/Document/Graphics/ColorTables/ncl_default.shtml]色标
* 波浪号('~')用于[function code][http://www.ncl.ucar.edu/Document/Graphics/function_code.shtml]