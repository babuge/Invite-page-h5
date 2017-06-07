(function ($) {
    $.getUrlParam = function (name) {
        var reg = new RegExp("(^|&)" + name + "=([^&]*)(&|$)");
        var r = window.location.search.substr(1).match(reg);
        if (r != null) return unescape(r[2]); return null;
    }
})(jQuery);
$(function(){
    var uid="uid";
    var qustAnswer=[];
    var uid_name="衣级";
    var baby="products";
    $(".u-name").html(uid_name);
    //设备高宽
    var devicesW=$(window).width();
    var devicesH=$(window).height();
    //slide 高
    $(".slide").css({"width":devicesW+"px"});
    //高=宽
    function hw(theW,times){
        if(!times){
            times=1;
        }
        theW.css({"height":theW.width()*times+"px"});
    }
    hw($(".addr-box"),0.67);
    $(".addr-box").children("li").css({"fontSize":devicesW*0.036+"px"});

    //json地址
    var citydata="",str="";
    $.getJSON("ChineseCities.json",function(data){
        citydata=data;
        data.forEach(function(data,index){
            //index可以作为二级联动的一个编号
            str+="<option value="+index+">"+data.name+"</option>";
        })
        $(".selectOne").append(str);
        });
    //第二级联动 sheng添加change事件
    var cityid="";
    var txt1="",txt2="";//为ajax传数据这儿用不着
    $(".selectOne").change(function(){
        cityid=$(".selectOne").val();//获取select选中的value
        $(".selectTwo").empty();//情况该元素的所有子节点，remove清除该元素
        var str="<option value='x'>请选择</option>";
        citydata[cityid].city.forEach(function(data,index){
            str+="<option value="+index+">"+data.name+"</option>";
        })
        $(".selectTwo").append(str);
    });
    //联动end=====
    //用户名验证--2-5汉字
    function isNC(str){
        var reg=/^[\u4E00-\u9FA5]+$/g;
        if(reg.test(str)){
            return true;
        }
        else{
            return false;
        }
    }
    //用户名验证--2-5汉字
    function isAd(str){
        var reg=/^(?=.*?[\u4E00-\u9FA5])[\dA-Za-z\u4E00-\u9FA5]+$/g;
        if(reg.test(str)){
            return true;
        }
        else{
            return false;
        }
    }
    //验证是否为空
    function  isNull(str){
        if(str==""){
            return true;
        }
        var reg=/^[ ]+$/g;
        return reg.test(str);
    }
    //验证手机号
    function isPhone(str){
        var reg=/^1[34578]\d{9}$/g;
        if(reg.test(str)){
            return true;
        }
    }
    //page-高

    if(devicesW<360){
        $(".contAddr").height(570);
    }else if( devicesH<640){
        $(".contAddr").height(640);
    }else{
        $(".contAddr").height(devicesH+20);
    }
    //人物高
    hw($(".pers-addr"));
    if($(".contAddr").height()<devicesH){
        $(".contAddr").height(devicesH);
    }
    
    $(".addrP").css({"fontSize":devicesW*0.055+"px"});
    $(".addrBtn").click(function(){
        var nameU=$(".intName").val(),
            addrMin=$(".detilAddr").val(),
            phoneNum=$(".phoneNum").val();
        txt1=$(".selectOne").find("option:selected").text();//获取select选中的内容
        txt2=$(".selectTwo").find("option:selected").text();//获取select选中的内容
        if(isNull(nameU)){
            $(".errorHint").show().html("姓名不能为空哦！");
            setTimeout(function(){$(".errorHint").hide()},3000);
            return;
        }
        if(!isNC(nameU)){
            $(".errorHint").show().html("姓名不符啦！");
            setTimeout(function(){$(".errorHint").hide()},3000);
            return;
        }
        if(txt1=="省份"||!txt1){
            $(".errorHint").show().html("要选择省份哦！");
            setTimeout(function(){$(".errorHint").hide()},3000);
            return;
        }
        if(txt2=="请选择"||txt2=="市"||!txt2){
            $(".errorHint").show().html("要选择市的！");
            setTimeout(function(){$(".errorHint").hide()},3000);
            return;
        }
        if(isNull(addrMin)){
            $(".errorHint").show().html("一定要详细地址啦！");
            setTimeout(function(){$(".errorHint").hide()},3000);
            return;
        }
        if(!isAd(addrMin)){
            $(".errorHint").show().html("要正确的详细地址哦！");
            setTimeout(function(){$(".errorHint").hide()},3000);
            return;
        }
        if(isNull(phoneNum)){
            $(".errorHint").show().html("电话号码是不能空的！");
            setTimeout(function(){$(".errorHint").hide()},3000);
            return;
        }
        if(!isPhone(phoneNum)){
            $(".errorHint").show().html("号码不符合哦！");
            setTimeout(function(){$(".errorHint").hide()},3000);
            return;
        }
        var url="",
            datas={
                nameU:nameU,
                address:txt1+txt2+addrMin,
                phone:phoneNum
            }
        // $.ajax({
        //     url:"Home/Index/question",
        //     data:datas,
        //     type: 'POST',
        //     async: false,
        //     success: function(data){
        //         aa = JSON.parse(data);
        //         console.log(aa);
        //     }
        //
        // });
        // var dat=$.getUrlParam(u_name);
        var dat="衣级";
        window.location.href="closely.html?name="+dat;

    });











});
