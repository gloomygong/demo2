<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>
<input type="date" id="date2"><button id="start">开始</button>
<div class="count-down"></div>
</body>
<script type="text/javascript">
document.getElementById("start").onclick = run;
function run(){
    var endtime = new Date(document.getElementById("date2").value);
    var starttime = Date.now();
    var time = (endtime.getTime() - starttime)/1000;
    var day = parseInt(time / (60 * 60 * 24));
    var hours = parseInt(time / (60 * 60) % 24);
    var min = parseInt(time / 60 % 60);
    var sec = parseInt(time % 60);
    document.getElementsByClassName("count-down")[0].innerHTML = "<span>" + "距离设置时间还有" + day +"天" + hours + "小时" + min + "分" + sec + "秒" + "</span>";
    setTimeout(run,1000);
    if (time<=0) {
        document.getElementsByClassName("count-down")[0].innerHTML = "时间到了";
    }
}
</script>
</html>
