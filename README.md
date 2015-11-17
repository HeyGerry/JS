# js循环绑定事件
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Document</title>
  <script>
  window.onload = function(){
    var  box1 = document.getElementById('box1');
    var oli = box1.children;
    var length = box1.children.length;
    console.log(oli[0]);

    // 方法一：
    // for(var i=0; i<length; i++){
    //   oli[i].onclick = (function(index){
    //     return function(){ console.log(index)}
    //   })(i);

    // }

    // 方法二：
    for(var i=0; i<length; i++){
      (function(index){
        oli[index].onclick = function(){
          console.log(index);
          console.log(oli[index]);
        }
      })(i);
    }


  }

  </script>
</head>
<body>
  <ul id="box1">
    <li>
      1111
    </li>
    <li>
      2222
    </li>
    <li>
      3333
    </li>
    <li>
      4444
    </li>
    <li>
      5555
    </li>
  </ul>

</body>
</html>
