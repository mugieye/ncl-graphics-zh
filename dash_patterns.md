**线条样式**

有17种[预定义的线条样式](http://www.ncl.ucar.edu/Document/Graphics/Images/dashpatterns.png)可用（样式０是实线）。你可以修改class="GraphicStyle">gsLineDashPattern中的gsLineDashPattern来设置线条样式，或者用 [gsn_add_polyline](http://www.ncl.ucar.edu/Document/Graphics/Interfaces/gsn_add_polyline.shtml)， [gsn_polyline](http://www.ncl.ucar.edu/Document/Graphics/Interfaces/gsn_polyline.shtml)， [gsn_polyline_ndc](http://www.ncl.ucar.edu/Document/Graphics/Interfaces/gsn_polyline_ndc.shtml)。

比如xy图表，用[xyDashPattern](http://www.ncl.ucar.edu/Document/Graphics/Resources/xy.shtml#xyDashPattern)或者[xyDashPatterns](http://www.ncl.ucar.edu/Document/Graphics/Resources/xy.shtml#xyDashPatterns)（大于一条线的图表）。

修改线条样式用0到16之间的整数，默认的值是0（实线）。

你可以用[NhlNewDashPattern](http://www.ncl.ucar.edu/Document/Functions/Built-in/NhlNewDashPattern.shtml)函数创建自己的虚线样式。参考XY application的[示例3](http://www.ncl.ucar.edu/Applications/xy.shtml#ex3)。

**Application示例**
* [polylines](http://www.ncl.ucar.edu/Applications/polyg.shtml)
* [XY图表](http://www.ncl.ucar.edu/Applications/xy.shtml)

**代码片段**
```
res                    = True
res@gsLineDashPattern  = 4    
res@xyDashPattern      = 4    
res@xyDashPatterns     = (/2,5,12/)
setvalues obj
   "gsLineDashPattern" :  4
   "xyDashPattern"     :  4
   "xyDashPatterns"    :  (/2,5,12/)
end setvalues
```
