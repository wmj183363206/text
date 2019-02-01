
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">    
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <meta http-equiv="Content-Type" content="text/html;charset-UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>无缝滚动轮播</title>
    <style type="text/css">
        *
        {
            padding:0px;
            margin:0px;
        }
        ul,ol
        {
            list-style:none;
        }
        .box
        {
            width:600px;
            height:500px;
            position:relative;
            left:35%;
        }
        .pic
        {
            width:600px;
            height:500px;
            overflow: hidden;           
            position:relative;
        }
        .box ul
        {
            width:5000px;
            position: absolute;
        }
        .box ul li
        {
            float:left;
            left:0;
            top:0;
        }
        .box ol
        {
            position: absolute;
            bottom:-25px;
            left:40%;
        }
        .box ol li
        {
            float:left;
            width: 10px;
            height:8px;
            background: url(pic/00.jpg) no-repeat;
           margin-left: 6px;
           
        }
        .box ol li .sub
        {
            background-position: right;
        }
        .left,.right
        {
            width: 233px;
            height:194px;
            position:absolute;
            top:42%;
            margin-top:-26px;
            background: url(pic/05.jpg) no-repeat;
        }
        .left
        {
            left:-235px;
        }
        .right
        {
            background-position: top right;
            left:605px;
        }
    </style>
    <script type="text/javascript" src="iquery.js"></script>
    <script type="text/javascript" src="max.js"></script>
</head>
<body>
    <div class="box">
        <div class="pic">
            <ul>
                <li><img src="pic/01.jpg" width="600px"  height="500px" alt=""/></li>
                <li><img src="pic/02.jpg" width="600px"  height="500px" alt=""/></li>
                <li><img src="pic/03.jpg" width="600px"  height="500px" alt=""/></li>
                <li><img src="pic/04.jpg" width="600px"  height="500px" alt=""/></li>
                <li><img src="pic/01.jpg" width="600px"  height="500px" alt=""/></li>
            </ul>
        </div>

        <a href="#" class="left"></a>
        <a href="#" class="right"></a>

        <ol>
            <li class="sub"></li>
            <li></li>
            <li></li>
            <li></li>
        </ol>
    </div>
</body>
<script type="text/javascript">

$(document).ready(function(){
  
  var num=1;
  var speed=1000;

  $(".right").click(function(event){
      num++;
  if(num>5){
   num=2;
  $(".box ul").css("left","0px");
  }
  $(".box ul").stop().animate({"left":-num*400},speed);
  
  circle++;
  if(circle>4){
      ciecle=1;
  }
  $(".box ol li").eq(circle).addClass("sub").substringlings().removeClass(".sub");
  });

//////////////////////////////////////////////////////
  $(".left").click(function(event){
      num--;
  if(num<1){
   num=4;
  $(".box ul").css("left","-2400px");
  }
  $(".box ul").stop().animate({"left": num*400},speed);
  
  circle++;
  if(circle<1){
      ciecle=4;
  }
  $(".box ol li").eq(circle).addClass("sub").substringlings().removeClass(".sub");
  });
});

</script>
</html>
