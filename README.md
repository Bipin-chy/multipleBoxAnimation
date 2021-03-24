
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Animation</title>

    <style>
        *{
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            text-align: center;
            
        }
        .container{
            width: 1040px;
            height: 400px;
            background-color: brown;
            position: relative;
            left: 12%;
            margin-top: 20px;
            margin-bottom: 20px;
        }
        #animated-box{
            width: 100px;
            height: 100px;
            background-color: #ffc93c;
            position: absolute;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        #animated-circle{
            width: 100px;
            height: 100px;
            background-color: #a37f22;
            position: absolute;
            border-radius: 50%;
        }

        #btn{
            padding: 10px 20px;
            outline: none;
            border: none;
            border-radius: 5px;
            background-color: brown;
            color: white;
        }

        #btn:hover{
            
            background-color: rgb(150, 8, 8);
            color: white;
        }
    </style>
</head>
<body>
    <h1>Box Animation</h1>
    <div class="container">
        <div id="animated-circle">

        </div>
        <div id="animated-box">
            Hello
        </div>
    </div>

    <button id="btn"  onclick="animation();">Click Me to animate</button>

    <script>
     
        function animation(){
           
            let animation = document.querySelector("#animated-box");
            let animationCircle = document.querySelector("#animated-circle");
            let animationHeight = animation .clientHeight;
            let animationWidth = animation .clientWidth;
            let animationCircleHeight = animationCircle.clientHeight;
            let animationCircleWidth = animationCircle.clientWidth;
            let containerHeight = document.querySelector(".container").clientHeight;
            let containerWidth = document.querySelector(".container").clientWidth;
            console.log(containerHeight);
           
            var boxPositionX = 0;
            var boxPositionY = 0;
            var boxPositionX1 = 0;
            var boxPositionY1 = 0;
            var speed = 1;
            var speed1 = 1;

            var speed2 = 5;
            var speed3 = 5;
            
            setInterval(frame,5);
            setInterval(frameCircle,10);
            function frame(){

                if(boxPositionX < (containerHeight - animationHeight)  ){
                    
                    animation.style.left =  boxPositionY  + 'px';
                    animation.style.top  =  boxPositionX + 'px';
                    
                }

                if(boxPositionX > (containerHeight - animationHeight) ){
                    
                    animation.style.top=  boxPositionX + 'px';
                    animation.style.left =  boxPositionY  + 'px';
                    
                    speed = -1;
                   
                    
                }

                if(boxPositionX < 0 ){
                    
                    animation.style.left =  boxPositionY  + 'px';
                    animation.style.top=  boxPositionX + 'px';
                    speed = 1;
                    
                }

                if( boxPositionY > (containerWidth - animationWidth) ){
                    animation.style.top=  boxPositionX + 'px';
                    animation.style.left =  boxPositionY  + 'px';
                    speed1 = -1;
                }

                if( boxPositionY < 0 ){
                    animation.style.top=  boxPositionX + 'px';
                    animation.style.left =  boxPositionY  + 'px';
                    
                    speed1 = 1;
                }

                        boxPositionX = boxPositionX + speed;
                        boxPositionY = boxPositionY + speed1;

            }
                function frameCircle(){

                        if(boxPositionX1 < (containerHeight - animationCircleHeight)  ){
    
                            animationCircle.style.left =  boxPositionY1  + 'px';
                            animationCircle.style.top=  boxPositionX1 + 'px';
                        }

                if(boxPositionX1 > (containerHeight - animationCircleHeight) ){
    
                            animationCircle.style.top=  boxPositionX1 + 'px';
                            animationCircle.style.left =  boxPositionY1  + 'px';
                            speed2 = -5;
                        }

                        if(boxPositionX1 < 0 ){
    
                            animationCircle.style.left =  boxPositionY1  + 'px';
                            animationCircle.style.top=  boxPositionX1 + 'px';
                            speed2 = 5;
    
                        }

                        if( boxPositionY1 > (containerWidth - animationCircleWidth) ){
                            animationCircle.style.top=  boxPositionX1 + 'px';
                            animationCircle.style.left =  boxPositionY1  + 'px';
                            speed3 = -5;
                        }

                        if( boxPositionY1 < 0 ){
                            animationCircle.style.top=  boxPositionX1 + 'px';
                            animationCircle.style.left =  boxPositionY1  + 'px';
                            speed3 = 5;
                        }
                        boxPositionX1 = boxPositionX1 + speed2;
                        boxPositionY1 = boxPositionY1 + speed3;

                }

}

// setTimeout(animation,5000);
            
    </script>
    
</body>
</html>
