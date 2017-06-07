(function ($) {
    $.getUrlParam = function (name) {
        var reg = new RegExp("(^|&)" + name + "=([^&]*)(&|$)");
        var r = window.location.search.substr(1).match(reg);
        if (r != null) return unescape(r[2]); return null;
    }
})(jQuery);
$(function(){
    //设备高宽
    var devicesW=$(window).width();
    var devicesH=$(window).height();
    //高=宽
    function hw(theW,times){
        if(!times){
            times=1;
        }
        theW.css({"height":theW.width()*times+"px"});
    }
    //初始化宽高度
    hw($(".bubble_down"),0.644);
    hw($(".pres_down"));
    hw($(".sun_light"));
    hw($(".logo_box"));
    hw($(".down_txt"),0.17);
    $(".down_andr").css({"width":devicesW*0.3+"px"});
    $(".down_ios").css({"width":devicesW*0.3+"px"});
    hw($(".down_andr"),0.28);
    hw($(".down_ios"),0.28);
    if($(".cont_down").height()<devicesH){
        $(".cont_down").height(devicesH);
    }
    
    
    
    
    
    
    
    
    
    
    
    
});