原标题效果：  
<img src="./src/Guilty Hole.original.gif" />

静态截图：  
<img src="./src/Guilty Hole.original.png">

## 断蜜
```lua
{\an8\pos(960,750)\fnVDL-LineGR B\fs200\3c&HFF52FF&
\t(!ksy.fdur(41)!,!ksy.fdur(41)!,\bord3\blur3)\t(!ksy.fdur(46)!,!ksy.fdur(48)!,\bord0\blur0)
!ksy.eff("ksy.func(function ()
    flag = not flag
    return flag and '\\\\bord3\\\\blur3' or '\\\\bord3\\\\blur2'
end).run()").genAniF(2,2,54,86)!
}{\alpha&HFF&}禁{\alpha&H00&}{\alpha&HFF&
!ksy.func(function ()
    ALPHA = "6FFFFF6F5FFFFF5F0000002F0000000F0000005F1F00"
end).run()!
!ksy.eff("ksy.func(function ()
    local _alpha = ALPHA:sub(1,2)
    ALPHA = ALPHA:sub(3)
    return '\\\\alpha&H'.._alpha..'&'
end).run()").genAniF(0,1,1,23)!}断
{\alpha&HFF&!ksy.func(function ()
    ALPHA = "FFFFFFBF6F3F6FFF5F1F000000000000000000000000"
end).run()!
!ksy.eff("ksy.func(function ()
    local _alpha = ALPHA:sub(1,2)
    ALPHA = ALPHA:sub(3)
    return '\\\\alpha&H'.._alpha..'&'
end).run()").genAniF(0,1,1,23)!}蜜
{\alpha&HFF&}域
```
禁字和域字单独处理，断字和蜜字主要是透明度和边框高斯模糊的动态效果。  
边框宽度和高斯模糊强度可以视作一组往复改变的效果，透明度则是需要逐帧选取一个近似值。
<img src="./src/Guilty Hole.断蜜.png">

## 禁
```lua
{\an7\p1\pos(
!960-ksy.str("禁断",ksy.func(function()
    local styleref = ksy.copy(_G.line.styleref)
    styleref.fontname = "VDL-LineGR B"
    styleref.fontsize = 200
    styleref.align = 8
    titlestyleref = styleref
    return styleref
end).run()).getw()+ksy.str("禁",titlestyleref).getw()*0.5!
,750)\alpha&H6F&
!ksy.func(function ()
    ALPHA = "9FFF9F3FFFFF2F00002F1F00001F00006F3F000000"
end).run()!
!ksy.eff("ksy.func(function ()
    local _alpha = ALPHA:sub(1,2)
    ALPHA = ALPHA:sub(3)
    return '\\\\alpha&H'.._alpha..'&'
end).run()").genAniF(0,1,1,22)!
\3c&HFF52FF&\t(!ksy.fdur(41)!,!ksy.fdur(41)!,\bord3\blur3)\t(!ksy.fdur(46)!,!ksy.fdur(48)!,\bord0\blur0)
!ksy.eff("ksy.func(function ()
    flag = not flag
    return flag and '\\\\bord3\\\\blur3' or '\\\\bord3\\\\blur2'
end).run()").genAniF(2,2,54,84)!
!ksy.t1!
!ksy.str("禁",titlestyleref).toshape().split().out(1).filter(function (shape,_,index)
    if index == 1 then
        shape = ksy.shape(shape).cutout(ksy.star(5,20,12,-50).fsc(.95).move(67,31).reverse().out(1)).out(1)
    end
    return shape
end).join(" ")!
!ksy.star(5,20,12,-50).fsc(.95).bord(6,true,2).move(67,31).reverse().out(1)!
!ksy.t2!
\t(!ksy.fdur(30)!,!ksy.fdur(40)!,\1c&H60FAFA&)
!ksy.t1!
!ksy.star(5,20,12,4).fsc(.5).bord(3,false,2).move(-68,-133).reverse().out(1)!
!ksy.t2!}
```
这个禁字如果以简单的方法做，可以另外起几行画右上角的五角星。  
其中比较麻烦的是，如果要在一行内实现，要将禁字与五角星内部重叠的部分裁剪掉，以及五角星必须生成圆角边的。  
五角星在中途会变成黄色。
<img src="./src/Guilty Hole.禁.png">

## 域
```lua
{\an7\p1\pos(!960+ksy.str("蜜域",titlestyleref).getw()-ksy.str("域",titlestyleref).getw()*0.5!,750)\alpha&HFF&
!ksy.func(function ()
    ALPHA = "FFFFFFFFFFFFFF5F0000001F0000000F0000006F2F00"
end).run()!
!ksy.eff("ksy.func(function ()
    local _alpha = ALPHA:sub(1,2)
    ALPHA = ALPHA:sub(3)
    return '\\\\alpha&H'.._alpha..'&'
end).run()").genAniF(0,1,1,23)!
\3c&HFF52FF&\t(!ksy.fdur(41)!,!ksy.fdur(41)!,\bord3\blur3)\t(!ksy.fdur(46)!,!ksy.fdur(48)!,\bord0\blur0)
!ksy.eff("ksy.func(function ()
    flag = not flag
    return flag and '\\\\bord3\\\\blur3' or '\\\\bord3\\\\blur2'
end).run()").genAniF(2,2,54,84)!
!ksy.t1!
!ksy.str("域",titlestyleref).toshape().split().out(1).removeAt(2).join(" ")!
!ksy.t2!
\t(!ksy.fdur(30)!,!ksy.fdur(40)!,\1c&H60FAFA&)
!ksy.t1!
!ksy.star(5,20,12,-12).fsc(1.25).bord(4,false,2).move(-153,25).out(1)!
!ksy.t2!}
```
<img src="./src/Guilty Hole.域.png">

## 遮罩
```lua
{\an7\p1\pos(960,750)\1c&H000000&\be8\blur60
\t(!ksy.fdur(23)!,!ksy.fdur(40)!,\fscx0)\t(!ksy.fdur(30)!,!ksy.fdur(40)!,\alpha&HFF&)
\clip(0,720,1920,1080)
!ksy.t1!
!ksy.square(ksy.str("禁断蜜域",titlestyleref).getw()*1.2,ksy.str("禁断蜜域",titlestyleref).geth()+120)
.move(0,ksy.str("禁断蜜域",titlestyleref).geth()*.5).out(0)!
!ksy.t2!}
```
点缀部分的出现效果不是简单的\fad，是从外圈到内部逐渐增加不透明度。  
背景刚好是纯黑色，直接放一行黑色的高斯模糊遮罩挡住点缀层是最简单的。

## 点缀
```lua
{\an7\p1\pos(0,0)\1c&H60FAFA&\alpha&HFF&\t(!ksy.fdur(23)!,!ksy.fdur(35)!,\alpha&H00&)
\3c&HFF52FF&\t(!ksy.fdur(41)!,!ksy.fdur(41)!,\bord4\blur4)\t(!ksy.fdur(46)!,!ksy.fdur(48)!,\bord0\blur0)
!ksy.eff("ksy.func(function ()
    flag = not flag
    return flag and '\\\\bord4\\\\blur4' or '\\\\bord2\\\\blur2'
end).run()").genAniF(2,2,54,84)!
!ksy.t1!
!ksy.star(4,10,4,0).bord(2,false,2).fsc(.88).move(798,912).out(1)!
 !ksy.star(4,10,4,0).bord(2,false,2).fsc(.92).move(956,816).out(1)!
 !ksy.star(4,10,4,0).bord(2,false,2).fsc(.82).move(958,906).out(1)!
 !ksy.star(4,10,4,0).bord(2,false,2).fsc(.98).move(1124,884).out(1)!
 !ksy.star(4,10,4,0).bord(2,false,2).fsc(.78).move(1172,784).out(1)!
 !ksy.circle(5).move(800,846).out(1)!
 !ksy.circle(4).move(938,820).out(1)!
 !ksy.circle(5).move(1088,782).out(1)!
 !ksy.circle(5).move(1022,842).out(1)!
 !ksy.circle(4).move(1131,868).out(1)!
!ksy.t2!}
```
<img src="./src/Guilty Hole.点缀.png">

## 渐变
```lua
{\an7\p1\pos(0,0)\1c&HFFFFFF&\be20\blur60\alpha&HFF&\t(!ksy.fdur(39)!,!ksy.fdur(45)!,\alpha&H00&)
\clip(
!ksy.str("蜜",titlestyleref).toshape().move(960,750).move(ksy.str("蜜",titlestyleref).getw()*.5).out(0)!
 !ksy.str("域",titlestyleref).toshape().move(960,750).move(ksy.str("蜜域",titlestyleref).getw()-ksy.str("域",titlestyleref).getw()*.5)
.split().out(0).removeAt(2).join(" ")!)
!ksy.t1!
!ksy.square(190,500).reset(8).move(960,720).out(0)!
!ksy.t2!
\1c&HFF52FF&\t(!ksy.fdur(39)!,!ksy.fdur(45)!,\alpha&HA0&)
!ksy.t1!
!ksy.square(180,500).reset(8).move(960,720).out(0)!
!ksy.t2!
\1c&HDBE008&\t(!ksy.fdur(39)!,!ksy.fdur(45)!,\alpha&HB0&)
!ksy.t1!
!ksy.square(200,500).reset(8).move(960,720).out(0)!
!ksy.t2!}
```
原本特效里后面几个字的内部有渐变效果，这是很难通过基础滤镜实现的。  
简单的思路就是放三个矩形加高斯模糊充当渐变，再用\clip裁剪到字体区域。
<img src="./src/Guilty Hole.渐变.png">

## 蜂窝
```lua
{\an7\p1\pos(0,0)\1c&HFF52FF&\alpha&HFF&\t(!ksy.fdur(39)!,!ksy.fdur(45)!,\alpha&HA0&)
\clip(
!ksy.str("蜜",titlestyleref).toshape().move(960,750).move(ksy.str("蜜",titlestyleref).getw()*.5).out(0)!
 !ksy.str("域",titlestyleref).toshape().move(960,750).move(ksy.str("蜜域",titlestyleref).getw()-ksy.str("域",titlestyleref).getw()*.5)
.split().out(0).removeAt(2).join(" ")!)
!ksy.t1!
!ksy.func(function()
    local d = 15
    local x1, x2, y1, y2 = 960, 960 + ksy.str("蜜域", titlestyleref).getw(), 760, 760 + ksy.str("蜜域", titlestyleref).geth()
    local h = ksy.round(d * math.sqrt(3) / 2, 2)
    local result1, result2, result3 = ksy.table(), ksy.table(), ksy.table()
    local row = 0
    local y = y1
    local eps = 1e-9
    while y <= y2 + eps do
        row = row + 1
        local offset = (row % 2 == 0) and (d / 2) or 0
        local startX = x1 - d
        local x = startX + offset
        local col = 0
        while x <= x2 + d + eps do
            if x >= x1 - eps and x <= x2 + eps then
                col = col + 1
                if x < 1090 then
                    result1.add(ksy.circle(3).move(x, y).out(1))
                elseif x < 1190 then
                    result2.add(ksy.circle(3).move(x, y).out(1))
                else
                    result3.add(ksy.circle(3).move(x, y).out(1))
                end
            end
            x = x + d
        end
        y = y + h
    end
    result1 = ksy.shape(result1.join(" "))
    result2 = ksy.shape(result2.join(" ")).move(-result1.width)
    result3 = ksy.shape(result3.join(" ")).move(-result2.width - result1.width)
    return result1.out(1) .. ksy.t2 ..
        "\\\\1c&HFCA1AA&" .. ksy.t1 .. result2.out(1) .. ksy.t2 ..
        "\\\\1c&HFDE373&" .. ksy.t1 .. result3.out(1)
end).run()!
!ksy.t2!}
```
生成蜂窝排列的圆。  
但其实一个更好的方法是用这些绘图当\clip，放多个矩形加高斯模糊模拟渐变。  
另外其实原效果中还有网格效果，这个要实现会大大增加绘图复杂度，特效容易卡顿得不偿失。
<img src="./src/Guilty Hole.蜂窝.png">

## 边框
```lua
{\an7\p1\pos(960,750)\1c&HFFFFFF&\3c&HFF52FF&
\t(!ksy.fdur(41)!,!ksy.fdur(41)!,\bord4\blur4)\t(!ksy.fdur(46)!,!ksy.fdur(48)!,\bord0\blur0)
!ksy.eff("ksy.func(function ()
    flag = not flag
    return flag and '\\\\bord4\\\\blur4' or '\\\\bord2\\\\blur2'
end).run()").genAniF(2,2,54,84)!}{
!ksy.t1!
!ksy.func(function ()
    local startX, endX, frames, radius, shrink1, shrink2, r = 1200, 756, 6, 10, 8, 16, 25
    local dcenter = math.abs(960-startX)-radius/2
    local width = dcenter + ksy.str("蜜域",titlestyleref).getw()-r+8
    local height = ksy.str("禁断蜜域",titlestyleref).geth()-r*2
    local t = function (n)
        return "\\alpha&HFF&\\t(" .. ksy.fdur(n) .. "," .. ksy.fdur(n) .. ",\\alpha&H00&)"
    end
    local corner = ksy.square(r*math.sqrt(2), 1).reset(4).move(-r*math.sqrt(2)/2).sampling(.5).filter(function (x, y)
        return ksy.xy(x, y).arcseg(0,0,r*math.sqrt(2),0,-100,0)
    end).rotate(0,0,0,0,45).bord((radius-1)/2,false,2)
    local shapes = ksy.table()
    shapes = shapes.add(
        ksy.line(width/frames, radius).move(-dcenter, shrink1).out(1),
        ksy.line(width/frames, radius).move(-dcenter+width/frames, shrink1).out(1),
        ksy.line(width/frames, radius).move(-dcenter+width/frames*2, shrink1).out(1),
        ksy.line(width/frames, radius).move(-dcenter+width/frames*3, shrink1).out(1),
        ksy.line(width/frames, radius).move(-dcenter+width/frames*4, shrink1).out(1),
        ksy.line(width/frames, radius).move(-dcenter+width/frames*5, shrink1).out(1),
        corner.move(r*math.sqrt(2)/2,r*(1-math.sqrt(2)/2)).move(width-dcenter, shrink1).out(1),
        ksy.line(height-shrink1-shrink2, radius).rotate(0,0,0,0,90).move(width-dcenter+r, shrink1+r).out(1),
        corner.rotate(0,0,0,0,90).move(r*math.sqrt(2)/2,r*math.sqrt(2)/2).move(width-dcenter, height+r-shrink2).out(1),
        ksy.line(ksy.str("蜜域",titlestyleref).getw()-r+6-math.abs(960-endX)-radius/2, radius).reset(6).move(radius/2)
            .move(width-dcenter, height+r*2-shrink2).out(1)
    )
    shapes.map(function (_, value)
        return ksy.shape(value).rotate(0,ksy.str("禁断蜜域",titlestyleref).geth()*.5+(shrink1-shrink2),0,0,180).out(1)
    end)
    mask2 = shapes.copy()
    shapes.fixshape()
    local result = ""
    for i=1, #shapes.value do
        result = result .. ksy.t2 .. t(26+i) .. ksy.t1 .. shapes.value[i]
    end
    return result
end).run()!
!ksy.t2!}
```
实际这样多个绘图加边框高斯模糊，边框重叠区域会颜色变深。但我觉得倒还更有一种溢出的效果，不暂停仔细看也注意不到。  
当然这里可能更大的问题是太复杂了。

## 边框
```lua
{\an7\p1\pos(960,750)\1c&HFFFFFF&\3c&HFF52FF&
\t(!ksy.fdur(41)!,!ksy.fdur(41)!,\bord4\blur4)\t(!ksy.fdur(46)!,!ksy.fdur(48)!,\bord0\blur0)
!ksy.eff("ksy.func(function ()
    flag = not flag
    return flag and '\\\\bord3\\\\blur3' or '\\\\bord2\\\\blur2'
end).run()").genAniF(2,2,54,84)!}{
!ksy.t1!
!ksy.func(function ()
    local startX, endX, frames, radius, shrink1, shrink2, r = 1200, 756, 6, 10, 8, 16, 25
    local dcenter = math.abs(960-startX)-radius/2
    local width = dcenter + ksy.str("蜜域",titlestyleref).getw()-r+8
    local height = ksy.str("禁断蜜域",titlestyleref).geth()-r*2
    local t = function (n)
        return "\\alpha&HFF&\\t(" .. ksy.fdur(n) .. "," .. ksy.fdur(n) .. ",\\alpha&H00&)"
    end
    local corner = ksy.square(r*math.sqrt(2), 1).reset(4).move(-r*math.sqrt(2)/2).sampling(.5).filter(function (x, y) return ksy.xy(x, y).arcseg(0,0,r*math.sqrt(2),0,-100,0) end).rotate(0,0,0,0,45).bord((radius-1)/2,false,2)
    local shapes = ksy.table()
    shapes = shapes.add(
        ksy.line(width/frames, radius).move(-dcenter, shrink1).out(1),
        ksy.line(width/frames, radius).move(-dcenter+width/frames, shrink1).out(1),
        ksy.line(width/frames, radius).move(-dcenter+width/frames*2, shrink1).out(1),
        ksy.line(width/frames, radius).move(-dcenter+width/frames*3, shrink1).out(1),
        ksy.line(width/frames, radius).move(-dcenter+width/frames*4, shrink1).out(1),
        ksy.line(width/frames, radius).move(-dcenter+width/frames*5, shrink1).out(1),
        corner.move(r*math.sqrt(2)/2,r*(1-math.sqrt(2)/2)).move(width-dcenter, shrink1).out(1),
        ksy.line(height-shrink1-shrink2, radius).rotate(0,0,0,0,90).move(width-dcenter+r, shrink1+r).out(1),
        corner.rotate(0,0,0,0,90).move(r*math.sqrt(2)/2,r*math.sqrt(2)/2).move(width-dcenter, height+r-shrink2).out(1),
        ksy.line(ksy.str("蜜域",titlestyleref).getw()-r+6-math.abs(960-endX)-radius/2, radius).reset(6).move(radius/2).move(width-dcenter, height+r*2-shrink2).out(1)
    )
    shapes.map(function (_, value)
        return ksy.shape(value).rotate(0,ksy.str("禁断蜜域",titlestyleref).geth()*.5+(shrink1-shrink2),0,0,180).out(1)
    end)
    mask2 = shapes.copy()
    shapes.fixshape()
    local result = ""
    for i=1, #shapes.value do
        result = result .. ksy.t2 .. t(26+i) .. ksy.t1 .. shapes.value[i]
    end
    return result
end).run()!
!ksy.t2!}
```
<img src="./src/Guilty Hole.边框.png">
此时加上边框的动态效果：
<img src="./src/Guilty Hole.边框动效.png">
只差最后给边框加上渐变。

## 渐变
```lua
{!maxloop(10)!
!ksy.retime(27+j-1,j~=maxj and (27+j) or nil)!
\an7\p1\pos(0,0)\1c&HFFFFFF&\be20\blur60
\clip(
!ksy.func(function ()
    local mask = ksy.table()
    for i=1, j do
        mask = mask.add(mask1.value[i])
        mask = mask.add(mask2.value[i])
    end
    mask.fixshape()
    return ksy.shape(mask.join(" ")).move(960,750).out(1)
end).run()!)
!ksy.t1!
!ksy.square(150,500).reset(8).move(960,720).out(0)!
!ksy.t2!
\1c&HFF52FF&\alpha&HA0&
!ksy.t1!
!ksy.square(180,500).reset(8).move(960,720).out(0)!
!ksy.t2!
\1c&HDBE008&\alpha&HB0&
!ksy.t1!
!ksy.square(250,500).reset(8).move(960,720).out(0)!
!ksy.t2!}
```
无法单行实现，所以生成了多行单帧特效。  
将边框的绘图重新用作\clip即可模拟渐变。
<img src="./src/Guilty Hole.渐变2.png">

## 最终效果
<img src="./src/Guilty Hole.full.gif">
