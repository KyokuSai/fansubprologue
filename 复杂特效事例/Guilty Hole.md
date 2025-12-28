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
