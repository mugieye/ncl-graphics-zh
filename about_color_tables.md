## About color tables

NCL自带有大量[预定义颜色表](http://www.ncl.ucar.edu/Document/Graphics/color_table_gallery.shtml) 。这些采用[RGB](http://www.ncl.ucar.edu/Document/glossary.shtml#RGB) 值的ASCII文件，安装在目录 $NCARG_ROOT/lib/ncarg/colormaps 下。

在NCL 6.2.0版本中，加入了超过一百种来自[ColorBrewer](http://colorbrewer2.org/#type=sequential&scheme=BuGn&n=3) ，[GMT](http://gmt.soest.hawaii.edu) ，[GrADS](http://www.iges.org/grads/) ，[matplotlib](http://matplotlib.org) ，以及[Ncview](http://meteora.ucsd.edu/~pierce/ncview_home_page.html) 的颜色表。它们大部分来自Nicolas Barrier，Melissa Bukovsky，与Carl Schreck的贡献。

NCL 6.1.0版本中的[缺省预定义颜色表](http://www.ncl.ucar.edu/Document/Graphics/ColorTables/ncl_default.shtml) ，称为“ncl_default”，具有256种颜色（包括背景及前景颜色）。旧版的[缺省颜色表](http://www.ncl.ucar.edu/Document/Graphics/ColorTables/hlu_default.shtml) 称为“default”，包含32种颜色。

如果你经常使用某一个预定义颜色表，可以在你的[.hluresfile](http://www.ncl.ucar.edu/Document/Graphics/hlures.shtml) 中加入这行代码：

`*wkColorMap : colormap_name`

其中，colormap_name是颜色表的名称，比如“[BlueWhiteOrangeRed](http://www.ncl.ucar.edu/Document/Graphics/ColorTables/BlueWhiteOrangeRed.shtml) ”。这个颜色表将成为你运行NCL时的新缺省值。

你可以[自定义颜色表文件](http://www.ncl.ucar.edu/Document/Graphics/create_color_table.shtml) ，并将其放置在NCL能直接下载的地方。你也可以使用预定义的[命名颜色](http://www.ncl.ucar.edu/Document/Graphics/named_colors.shtml) ，或者在NCL脚本中使用[RGB](http://www.ncl.ucar.edu/Document/glossary.shtml#RGB) ／[RGBA](http://www.ncl.ucar.edu/Document/glossary.shtml#RGBA) 数组，创建自定义的颜色表。如果需要参考应用举例，请浏览[colormap page](http://www.ncl.ucar.edu/Applications/colormap.shtml) 。

为了方便使用，你可以下载一个包含所有最新颜色表的tar file 。在文件解压到目录 $NCARG_ROOT/lib/ncarg/colormaps 下，或是解压到你的个人目录下，然后在此目录下setenv NCARG_COLORMAPS 。

Nicolas Barrier提供了一段NCL脚本[svgtocmap.ncl](http://www.ncl.ucar.edu/Document/Graphics/Scripts/svgtocmap.ncl) ，将来自于[http://soliton.vm.bytemark.co.uk/pub/cpt-city/] 的众多colormaps转化成NCL RGB colormaps。其中大部分colormaps都包含在NCL 6.2.0版本中。作为相关的兴趣拓展，有篇题为“[The End of the Rainbow? Color Schemes for Improved Data Graphics](http://geog.uoregon.edu/datagraphics/EOS/index.htm) ”的文章，提到了如何改善科学可视化colormaps。点击“PDF file”下载文章，或浏览一些PNG图片来比较color maps之间的区别。

### 分组

* [彩虹](http://www.ncl.ucar.edu/Document/Graphics/ColorTables/Rainbow_cat.shtml)
* [用于帮助色盲与颜色缺陷浏览者的颜色表](http://www.ncl.ucar.edu/Document/Graphics/ColorTables/Aid_in_color_blindness_cat.shtml)
* [MeteoSwiss使用的颜色表](http://www.ncl.ucar.edu/Document/Graphics/ColorTables/MeteoSwiss_cat.shtml)
* [中间为白色的颜色表](http://www.ncl.ucar.edu/Document/Graphics/ColorTables/White-in-the-middle_cat.shtml)

### 应用举例

* [使用命名的颜色](http://www.ncl.ucar.edu/Applications/color.shtml#ex4)
* [保存颜色表](http://www.ncl.ucar.edu/Applications/color.shtml#ex8)
* [CMYK](http://www.ncl.ucar.edu/Applications/color.shtml#ex11)
* [使用RGB值](http://www.ncl.ucar.edu/Applications/color.shtml#ex12)
* [HSV](http://www.ncl.ucar.edu/Applications/color.shtml#ex13)
* [改变前景／背景颜色](http://www.ncl.ucar.edu/Applications/color.shtml#ex14)
* [恢复colormap中的RGB值](http://www.ncl.ucar.edu/Applications/color.shtml#ex16)

### 代码段

```
;---Using the color map to define colors for contours or vectors
  res@cnFillPalette = "BkBlAqGrYeOrReViWh200"
  res@vcLevelPalette = "BkBlAqGrYeOrReViWh200"

;---Reading the colormap into an N x 4 (RGBA) array
  cmap = read_colormap_file("ncl_default")

;---Using the color map to define a color map for the workstation
  gsn_define_colormap(wks,"BlueYellowRed")
```

### 致谢

以下人士对NCL color tables的贡献已达多年：

* Adam Phillips, NCAR
* Nicolas Barrier, Laboratoire de Physique des Oceans
* Professor Patrick J. Bartlein, Dept. of Geography, University of Oregon
* Melissa Bukovsky, NCAR
* John Fasullo, NCAR
* Oliver Fuhrer, MeteoSwiss
* Joe Grim, NCAR
* Andrea Hahmann
* Matthew Long, NCAR
* Dennis Shea, NCAR
* Emilie Vanvye, NAR