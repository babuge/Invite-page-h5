$(function(){
        //问答
    var qustAnswer=[];
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
    //page-one
    hw($(".invite-bar").find(" dt"),168/142);
    hw($(".u-head"));
    hw($(".bubble-bar"),0.7);
    hw($(".pers-one"),0.8);
    hw($(".pers-four"),0.9);
    //btn-one
    if(devicesW<360){
        hw($("#btnOne"),0.3);
    }else{
        hw($("#btnOne"),0.4);
    }
    //btn-two-高-位置
    hw($("#btnTwo"),0.32);
    //btn-three-高
    hw($("#btnThree"),0.32);
    //btn-four-高
    hw($("#btnFour"),1.2);
    $(".u-call").css({"fontSize":devicesW*0.095+"px"});
    $(".u-name").css({"fontSize":devicesW*0.095+"px"});
    //ajax 问题及答案及干扰答案=====
    var aa="",questions=[],uAnswer=[],errAnswer=[];
    // $.ajax({
    //     url:"Home/Index/question",
    //     data:{
    //         uid:'1'
    //     },
    //     type: 'POST',
    //     async: false,
    //     success: function(data){
    //         aa = JSON.parse(data);
    //         console.log(aa);
    //     }
    //
    // });

    // for(var i=0;i<aa.length;i++){
    //     questions[i]=i+1+"."+aa[i].questions;
    //     uAnswer[i]=aa[i].right_answers;
    //     errAnswer[i]=aa[i].wrong_anwers;
    // }
    var questions=["1. 我是单身吗？","2. 我喜欢熬夜吗？ ", "3. 我喜欢裸睡吗？","4. 我有暗恋对象吗？ ","5. 小时候我被妈妈打过吗？"];
    var uAnswer=["不是","不喜欢","喜欢","有"," 有"];
    var errAnswer=["是","喜欢","不喜欢","没有","没有"];
    //========

    //问题答案方法
    function allAnswer(tags,num){
        //标签box编号
        var numTag;
        if(num%2==0){
            numTag=1;
        }else{
            numTag=2;
        }
        tags.find(".questBox"+numTag+"").find(".questOne").html(questions[num]);
        tags.find(".questBox1"+numTag+"").find("span").eq(0).html(errAnswer[num]);
        tags.find(".questBox2"+numTag+"").find("span").eq(1).html(uAnswer[num]);
    }
    //问题及答案选项
    allAnswer($('.questB-One'),0);
    allAnswer($('.questB-One'),1);
    allAnswer($('.questB-Two'),2);
    allAnswer($('.questB-Two'),3);
    allAnswer($('.questB-Three'),4);
    //记录答案与选择
    function qustSelect(tags,num,arr){
        tags.find(" .questBox"+num).find("input").each(function(i) {
            $(this).click(function () {
                tags.find(".questBox"+num).find(".answer_icon").css({"opacity": "0"});
                tags.find(".questBox"+num).find(".answer_icon").eq(i).css({"opacity": "1"});
                qustAnswer[arr]=i;
            })
        });
    }
    qustSelect($(".questB-One"),1,0);
    qustSelect($(".questB-One"),2,1);
    qustSelect($(".questB-Two"),1,2);
    qustSelect($(".questB-Two"),2,3);
    qustSelect($(".questB-Three"),1,4);
    //btn-one
    $("#btnOne").click(function(){
        $("#pageOne").css({"zIndex":2});
        $("#pageTwo").css({"zIndex":15});
        $("#pageTwo").show();
        $("#pageOne").remove();
    });
    //===pageTwo
   hw($(".bubble-bar1"),0.77);
    hw($(".pers-two"),0.9);
    hw($(".gift1"));
    hw($(".gift2"));
    //初始化图标
    $(".questBox1").find(".answer_icon").css({"opacity":"0"});
    $(".questBox2").find(".answer_icon").css({"opacity":"0"});
    $(".answer_icon").css({"width":devicesW*0.097+"px","height":devicesW*0.0844+"px"});
    //问题字size
    $(".questOne").css({"fontSize":devicesW*0.057+"px"});
    $(".selectBox").find("span").css({"fontSize":devicesW*0.046+"px"});

    //btn-two
    $("#btnTwo").click(function(){
        var checked=$(".questB-One").find("input:checked");
        if(checked.length==2){
            $("#pageTwo").css({"zIndex":3});
            $("#pageThree").css({"zIndex":15});
            $("#pageTwo").remove();
            $("#pageThree").stop().show();
        }else{
            $(".errorHint").show().html("一定要全部选择哦！");
            setTimeout(function(){$(".errorHint").hide()},3000);
            return ;
        }
    });
    //====height====
    var liH=$("#pageOne").height();
    $(".slide").children("div").css({"height":liH+"px"});
    if(liH<devicesH){
        $(".slide").children("div").css({"height":devicesH+"px"});
    }
    //page-three
    hw($(".bubble-bar2"),0.8);
    hw($(".gift3"));
    hw($(".gift4"));
    hw($(".pers-three"),0.8);
    //btn-three
    $("#btnThree").click(function(){
        var checked=$(".questB-Two").find("input:checked");
        if(checked.length==2){
            $("#pageThree").css({"zIndex":4});
            $("#pageFour").css({"zIndex":15});
            $("#pageThree").remove();
            $("#pageFour").stop().show();
        }else{
            $(".errorHint").show().html("一定要全部选择哦！");
            setTimeout(function(){$(".errorHint").hide()},3000);
            return;
        }
    });

    //page-Four
    hw($(".bubble-bar3"));
    hw($(".gift5"));
    hw($(".txt-bar"));
    $(".questB-Three").find("input").click(function(){
        $(".txt-bar").show();
        $(".newUser").show();
        $(".btnBxFour").show();
    });
        //用户名验证--2-5汉字
    function isNC(str){
        var reg=/^[\u4E00-\u9FA5]{2,5}$/g;
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
//无关用户名
    var inptVal="";
    var strb=0;
//button-event3
    $("#btnFour").click(function(){
        //无关用户名
        inptVal=$("#newUser").val();
        for(var x=0;x<number.length;x++){
            if(number[x]===qustAnswer[x]){strb++;}
        }
        var checked=$(".questB-Three").find("input:checked");
        if(checked.length!=1){
            return;
        }
        if(isNull(inptVal)){
            $(".errorHint").show().html("用户名不能为空哦！");
            setTimeout(function(){$(".errorHint").hide()},3000);
            return;
        }
        if(!isNC(inptVal)){
            $(".errorHint").show().html("用户名只能是大于两的中文啦！");
            setTimeout(function(){$(".errorHint").hide()},3000);
            return;
        }
        var uid=the_id;
        var url="",
            data={
            name:inptVal,       //被邀请人昵称
            trueNum:strb,    //正确个数
            uid:uid    //邀请人id
        };
        window.location.href="mubiao.html?id="+strb;
    });
    
});

