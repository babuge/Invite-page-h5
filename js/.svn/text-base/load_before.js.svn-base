(function ($) {
    $.getUrlParam = function (name) {
        var reg = new RegExp("(^|56&)" + name + "=([^&]*)(&|$)");
        var r = window.location.search.substr(1).match(reg);
        if (r != null) return unescape(r[2]); return null;
    }
})(jQuery);
var the_id="";
if(!$.getUrlParam("uid")){
    the_id="null";
}else{
    the_id=$.getUrlParam("uid");
}
// $.ajax({
//     'url':"../Home/Index/isuser",
//     'data':{
//         uid:the_id
//     },
//     'type': 'POST',
//     'success': function(data){
//         var aa = JSON.parse(data);
//         if(data==0){
//             alert(112221212121222212);
//             window.location.href="error.html";
//             return;
//         }
//     },
//     'async': false
// });