const  sw  =  800 ; 
const  sh  =  600 ; 
const  pixelRatio  =  2 ;

function  init ( )  { 
    canvas  =  document . createElement ( 'canvas' ) ; 
    문서 . 몸 . appendChild ( 캔버스 ) ; 
    ctx  =  캔버스 . getContext ( "2d" ) ;

    캔버스 . 너비  =  sw * pixelRatio ; 
    캔버스 . 높이  =  sh * pixelRatio ; 
    캔버스 . 스타일 . 너비  =  sw  +  'px' ; 
    캔버스 . 스타일 . 높이  =  sh  +  'px' ; 
    ctx . 스케일 ( pixelRatio ,  pixelRatio ) ;

    leon  =  new  LeonSans ( { 
        text : '빠른 갈색 \ n 여우가 게으른 개를 \ n 뛰어 넘습니다' , 
        색상 : [ '# 000000' ] , 
        크기 : 80 , 
        무게 : 200 
    } ) ;

    requestAnimationFrame ( 애니메이션 ) ; 
}

function  animate ( t )  { 
    requestAnimationFrame ( animate ) ;

    ctx . clearRect ( 0 ,  0 ,  sw ,  sh ) ;

    const  x  =  ( sw  -  leon . rect . w ) / 2 ; 
    const  y  =  ( sh  -  leon . rect . h ) / 2 ; 
    레온 . 위치 ( x ,  y ) ;

    레온 . 그리기 ( ctx ) ; 
}

창 . onload  =  ( )  =>  { 
    init ( ) ; 
} ;

내가 ,  합계  =  레온 하자 . 그리기 . 길이 ; 
for  ( i  =  0 ;  i  <  total ;  i ++ )  { 
    TweenMax . fromTo ( leon . drawing [ i ] ,  1.6 ,  { 
        value : 0 
    } ,  { 
        delay : i * 0.05 , 
        value : 1 , 
        ease: Power4 . easeOut 
    } ) ; 
}
