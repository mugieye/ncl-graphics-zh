**标记样式**

有17种[预定义标记](http://www.ncl.ucar.edu/Document/Graphics/Images/markers.png)。你可以用[gsMarkerIndex](http://www.ncl.ucar.edu/Document/Graphics/Resources/gs.shtml#gsMarkerIndex)更改多点标记或[gsn_add_polymarker](http://www.ncl.ucar.edu/Document/Graphics/Interfaces/gsn_add_polymarker.shtml),[gsn_polymarker](http://www.ncl.ucar.edu/Document/Graphics/Interfaces/gsn_polymarker.shtml),[gsn_polymarker_ndc](http://www.ncl.ucar.edu/Document/Graphics/Interfaces/gsn_polymarker_ndc.shtml)的样式。

对于散点图或包含标记的xy图表，用[xyMarker](http://www.ncl.ucar.edu/Document/Graphics/Resources/xy.shtml#xyMarker)或[xyMarkers](http://www.ncl.ucar.edu/Document/Graphics/Resources/xy.shtml#xyMarkers)（多条线的图表）来修改标记样式。

标记样式值的范围是整数0到16，默认值是0（星号）。

你也可以用[NhlNewMarker](http://www.ncl.ucar.edu/Document/Functions/Built-in/NhlNewMarker.shtml)函数创建自己的标记样式，参见XY application[示例4](http://www.ncl.ucar.edu/Applications/xy.shtml#ex4)。

**Application 例子**
* [多点标记](http://www.ncl.ucar.edu/Applications/polyg.shtml)
* [XY图表](http://www.ncl.ucar.edu/Applications/xy.shtml)

**代码片段**
```
res               = True
res@gsMarkerIndex = 4    
res@xyMarker      = 4    
res@xyMarkers     = (/2,5,12/)
setvalues obj
   "gsMarkerIndex":  4
   "xyMarker"     :  4
   "xyMarkers"    :  (/2,5,12/)
end setvalues
```
