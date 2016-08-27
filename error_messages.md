## Common Graphical Error Messages

#### 错误的坐标变量

```
    (0)    check_for_y_lat_coord: Warning: Data either does 
    not contain a valid latitude coordinate array or doesn't 
    contain one at all
    (0)    check_for_lon_coord: Warning: Data either does 
    not contain a valid longitude coordinate array or doesn't 
    contain one at all
```

gsn_csm 制图模板需要输入含有以下名称的lat/lon坐标组：

```
    lon, Lon, LON
    Longitude, longitude, LONGITUDE
    hlon,  long
    lon_u, lon_t
    xc
```

如果你使用的是地理坐标变量，用以上的名称重命名你的变量。



#### 坐标变量没有正确的单位属性

```
    (0)   is_valid_lat_ycoord: Warning: The units attribute of 
    the Y coordinate array is not set to one of the allowable 
    units values (i.e. 'degrees_north'). Your latitude labels 
    may not be correct.

    (0)   is_valid_lat_xcoord: Warning: The units attribute of 
    the X coordinate array is not set to one of the allowable 
    units values (i.e. 'degrees_east'). Your longitude labels 
    may not be correct.
```

除了正确的坐标变量名之外，lat/lon坐标组还必须拥有单位属性，格式如下：

```
    degrees_north, degree_north, degrees north, degrees_N
    degrees_east,  degree_east,  degrees east,  degrees_E
```

同样你可以重命名你的单位名称以遵守以上格式：

```
    x&lat@units="degrees_north"
    x&lon@units="degrees_east"
```



#### 非全球数据

```
     (0)  gsn_add_cyclic: Warning: The range of your longitude data is not 360.
     You may want to set gsnAddCyclic to False to avoid a warning
     message from the spline function.
```

一些gsn_csm制图模板需要全球数据。因此这些模板会在数据中加入循环点，以使制图正确。如果你的数据是非全球性的（如区域数据），将会收到报错信息。想要解决这个问题，你需要告诉模板不要添加循环点。

`        res@gsnAddCyclic = False`



#### 地图缩放技术

```
    (0) gsn_csm_map_ce: Warning: you cannot use mpLimitMode = xxxx with
    the gsm_csm_map routines.
```

只有[mpLimitMode](http://www.ncl.ucar.edu/Document/Graphics/Resources/mp.shtml#mpLimitMode)等同于“LatLon”，或者“Corners”能被该模板接受。



#### 非单调变化的坐标变量

```
    (0) warning:_NhlCreateSplineCoordApprox: Attempt to create spline
    approximation for Y axis failed: consider adjusting trYTensionF value
    warning:IrTransInitialize: error creating spline approximation for
    trYCoordPoints; defaulting to linear
```

Y（或X）轴数据间隔过于不规则，NCL无法将它们插值到线性轴中。

坐标变量中存在间隙时，经常会出现这种错误。The first step is to print out the deltas between the values in the coordinate array to see if they are constant.



#### 数据过大

```
    fatal:ContourPlotDraw: Workspace reallocation would exceed maximum size 16777216
    fatal:ContourPlotDraw: draw error
    fatal:PlotManagerDraw: error in plot draw
    fatal:_NhlPlotManagerDraw: Draw error
```

当你尝试绘制的结果大于16mb时，就会出现这个错误。一个1000x1000的网格数据肯定会产生这个错误，不过目前还没有确切的限制值。

想要修正这个错误，你可以转换成raster mode（res@[cnFillMode](http://www.ncl.ucar.edu/Document/Graphics/Resources/cn.shtml#cnFillMode)="RasterFill"），这样就不需要占用太大的内存，也不需要提高存储空间。后者可通过在打开workstation的语句后加入以下代码实现：

```
    setvalues NhlGetWorkspaceObjectId()
      "wsMaximumSize": 300000000
    end setvalues
```

你也可以在你的[.hluresfile](http://www.ncl.ucar.edu/Document/Graphics/hlures.shtml)中增加你的工作站存储空间：

`*wsMaximumSize: desired value`



#### [.hluresfile](http://www.ncl.ucar.edu/Document/Graphics/hlures.shtml)文件缺失

```
    PLCHHQ - CHARACTER NUMBER 16 (x) IS NOT A LEGAL FUNCTION CODE

    PLCHHQ - CHARACTER NUMBER 19 (b) IS NOT A LEGAL FUNCTION CODE
```

如果我们将.hluresfile文件中的缺省函数代码从“:”改成“~”，将影响目前网页上的所有应用案例。



#### ARSCAM/ARPRAM算法错误

