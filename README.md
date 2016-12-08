<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>포토갤러리</title>
    <link rel="stylesheet" type="text/css" href="http://tour.interpark.com/global/css/ui_common.css">
    <style>
    /* 팝업 가이드 */
    .popup-module {position:relative; padding-bottom:40px; font-family:'Nanum Gothic',malgun Gothic,dotum; border:1px solid #666; border:1px solid #7e8185; color:#6a6a6a; background:#fff;}
    .popup-module img {vertical-align:top;}
    .popup-module .ui-first-child {margin-top:0 !important; padding-top:0 !important;}
    .popup-module .tit-h1 {padding:17px 30px 20px 45px; font-size:18px; color:#fff; background:#7e8185 url("http://openimage.interpark.com/tourpark/tour_ui/common/icon/icon_arrow01_1.gif") no-repeat 30px 48%;}
    .popup-module .tit-h2 {margin-top:30px; padding-left:13px; font-size:15px; color:#333; background:url("http://openimage.interpark.com/tourpark/tour_ui/common/icon/icon_arrow01_3.gif") no-repeat 0 5px;}
    .popup-module .txt1.add1 {font-size:14px;}
    .popup-module .tit-type1:before {content:">"; display:inline-block; width:15px; height:14px; margin-right:5px; vertical-align:2px; padding-top:1px; background:#3da7bd; border-radius:30px; color:#fff; font-size:9px; font-weight:bold; text-align:center;}
    .popup-module .pop-close {position:absolute; top:17px; right:18px; font-size:0; line-height:0;}
    .popup-module .pop-close:before {content:"×"; display:block; width:25px; height:25px; font-size:30px; color:#fff; line-height:25px; font-weight:normal; font-family:dotum;}
    .popup-module .pop-dBody {position:relative; margin:0; padding:30px; padding:30px; padding:40px; padding-bottom:0;}
    .popup-module .dFoot {margin-top:20px; text-align:center;}

    /*포토갤러리*/
    .popup-module.photo-gallery {width:800px; padding-bottom:30px; background:#333333; border:0;}
    .popup-module.photo-gallery p {padding:0; margin:0}
    .popup-module.photo-gallery .tit-h1 {margin-left:0; padding-left:30px; background-image:none;}
    .popup-module.photo-gallery .tit-h1 .txt {display:inline-block; overflow:hidden; max-width:50%; margin-right:10px; vertical-align:top; white-space:nowrap; text-overflow:ellipsis;}
    .popup-module.photo-gallery .spot {font-size:13px;}
    .popup-module.photo-gallery .pop-dBody {padding:30px; padding-bottom:0;}
    .popup-module.photo-gallery .loc {position:absolute; top:-36px; right:70px; color:#fff;}
    .popup-module.photo-gallery .photo-block {overflow:hidden; display:table; width:100%; background:#222;}
    .popup-module.photo-gallery .photo-view {position:relative; display:table-cell; width:580px; overflow:hidden; height:435px; text-align:center; vertical-align:middle; background:#111;}
    .popup-module.photo-gallery .photo-view:before {position:absolute; left:40%; content:"NO IMAGE (580 × 435)"; z-index:0;}
    .popup-module.photo-gallery .photo-view .photo {position:relative; width:auto; max-width:580px; max-height:100%; z-index:1;}
    .popup-module.photo-gallery .photo-view .txt1 {overflow:hidden; position:absolute; bottom:0; left:0; width:100%; padding:10px 0; background: url("http://openimage.interpark.com/tourpark/tour_ui/free/bg_hover.png") repeat left top; color:#fff; text-align:center; z-index:2;}
    .popup-module.photo-gallery .photo-view .sub-data1 {float:left; margin-left:15px;}
    .popup-module.photo-gallery .photo-view .sub-data2 {float:right; margin-right:15px;}
    .popup-module.photo-gallery .movement {position:relative; display:table-cell; padding:28px 20px; height:379px;}
    .popup-module.photo-gallery .prev,
    .popup-module.photo-gallery .next {position:absolute; overflow:hidden; width:160px; height:28px; font-size:0; line-height:0;}
    .popup-module.photo-gallery .prev {top:0; left:0;}
    .popup-module.photo-gallery .next {bottom:0; left:0;}
    .popup-module.photo-gallery .prev:before,
    .popup-module.photo-gallery .prev:after,
    .popup-module.photo-gallery .next:before,
    .popup-module.photo-gallery .next:after {position:absolute; left:50%; margin-left:-10px; content:""; border:10px solid transparent;}
    .popup-module.photo-gallery .prev:before {top:0px;border-bottom:10px solid #fff;}
    .popup-module.photo-gallery .prev:after {top:2px; border-bottom:10px solid #222;}
    .popup-module.photo-gallery .next:before {bottom:0px; border-top:10px solid #fff;}
    .popup-module.photo-gallery .next:after {bottom:2px; border-top:10px solid #222;}

    .popup-module.photo-gallery .photo-list li {width:120px; height:90px; margin-top:5px; background:#444444;}
    .popup-module.photo-gallery .photo-list li:first-child {margin-top:0;}
    .popup-module.photo-gallery .photo-list li a {display:block; }
    .popup-module.photo-gallery .photo-list li img {width:120px; height:90px;}
    .popup-module.photo-gallery .photo-list li a:hover {border:2px solid #f30;overflow:hidden; width:116px; height:86px;}
    .popup-module.photo-gallery .photo-list li a:hover img {width:120px; height:90px; margin-top:-2px; margin-left:-2px;}

    .popup-module.photo-gallery .spot-view {overflow-y:auto; overflow-x:hidden; max-height:430px; padding:0 30px 30px; color:#bdbdbd; background:#444444;}
    .popup-module.photo-gallery .spot-view h2 {margin-top:30px; padding-top:30px; border-top:1px dashed #6a6a6a; font-size:18px; font-weight:bold; color:#fff;}
    .popup-module.photo-gallery .spot-view h2:first-child {margin-top:0; border-top:0;}
    .popup-module.photo-gallery .spot-view .para {margin-top:15px; line-height:25px;}
</style>

    <script src="https://code.jquery.com/jquery-1.10.2.js"></script>
</head>
<body>


<div class="popup-module photo-gallery">
    <h1 class="tit-h1"> 관광지명 <span class="spot">[놀이/테마공원] </span></h1>
    <div class="pop-dBody">
        <em class="loc">[지역] 태국 &gt; 방콕 &gt; 왕궁주변</em>
        <!-- 뷰영역 -->
        <div class="photo-block">
            <div class="photo-view">
                <img class="photo" src="http://tourimage.interpark.com//Spot/317/21856/201502/6355849271181607670.jpg" alt="상품 사진" />
                <p class="txt1"><span class="sub-data1">by 배짱이</span> <span class="sub-data2">dklsdkfjl</span></p>
            </div>
            <div class="movement">
                <button class="prev">이전</button>
                <ul class="photo-list">
                    <li class=""><a href="#"><img src="http://tourimage.interpark.com//Spot/317/21856/201502/6355849271181607670.jpg" alt=""></a></li>
                    <li class=""><a href="#"><img src="http://tourimage.interpark.com//Spot/317/21856/201502/6355849271183170182.jpg" alt=""></a></li>
                    <li class=""><a href="#"><img src="http://tourimage.interpark.com//Spot/317/21856/201502/6355849413819617030.jpg" alt=""></a></li>
                    <li class="on"><a href="#"><img src="http://tourimage.interpark.com//Spot/317/21856/201502/6355849413821179542.jpg" alt=""></a></li>
                </ul>
                <button class="next">다음</button>
            </div>
        </div>
        <!-- 스팟정보 -->
        <div class="spot-view">
            <h2 class="sub-tit">소개</h2>
            <div id="Intro" class="para"> 괌에서 가장 번화한 곳은 플레저 아일랜드의 면세점 DFS 갤러리아다. 이곳은 네 곳으로 구분되는데, 패션월드, 부티크 갤러리아, 뷰티월드, 데스티네이션월드가 있다. 패션월드에는 버버리, 지방시, 폴로, 랄프로렌, 엠포리오 알마니, 마크 제이콥스와 같은 캐주얼 의류 매장이 있고, 부티크 갤러리아에는 구찌, 프라다, 디올, 샤넬, 까르띠에, 루이비통, 몽블랑과 같은 고급 브랜드가 있다. 그리고 뷰티월드에는 향수를 비롯한 각종 화장품들이 있는데 랑콤이나 MAC, 크리스찬 디올, 샤넬, 슈에무라, 오리진 등 최고급 화장품 브랜드들이 입점해 있다. 또 지역 선물용품이나 기념품과 포도주를 살 수 있는 코너가 있어 발렌타인, 이니스킬린 아이스 와인 혹은 고디바 초콜릿 등과 같은 유명 브랜드의 상품을 구입할 수 있다. DFS 갤러리아에는 최근 한국인이 많이 찾아 한국인 취향에 맞는 제품들도 많고 무엇보다도 한국어를 하는 직원들이 있어 도움을 요청할 수 있다. 매장팜플렛을 구해서 다니면 편한 매장찾기에 유용하다. 식사나 가벼운 음료를 마실 때는 플래닛 할리우드나 스와레를 찾으면 된다. </div>
            <h2 class="sub-tit">주요정보</h2>
            <div class="para"><!-- DB 값 가져 오는 부분 -->
                *주소 : 1296 Pale San Vitores RoadTumon, Guam 96913<br>
                *전화번호 : 671-649-8097<br>
                *가는방법 : 플레저 아일랜드 내, 괌 어디에서나 택시를 타면 무료로 갈 수 있음<br>
                *오픈시간 : 10:00~23:00<br>
                *휴무일 : 토요일<br>
                *홈페이지 : www.dfsgalleria.com<br>
            </div>
            <h2 class="sub-tit">TIP</h2>
            <div class="para"><!-- DB 값 가져 오는 부분 -->
                *주소 : 1296 Pale San Vitores RoadTumon, Guam 96913<br>
                *전화번호 : 671-649-8097<br>
                *가는방법 : 플레저 아일랜드 내, 괌 어디에서나 택시를 타면 무료로 갈 수 있음<br>
                *오픈시간 : 10:00~23:00<br>
                *휴무일 : 토요일<br>
                *홈페이지 : www.dfsgalleria.com<br>
            </div>
        </div>
    </div>
    <button type="button" class="pop-close">닫기</button>
</div>

<script>
    $( ".photo-list li a" ).click(function() {
        var address = $(this).children("img");
        $(".photo-view img").attr("src",address.attr("src")).attr("alt",address.attr("alt"));
        $(this).parent().addClass("on").siblings().removeClass("on");
        return false;
    });
</script>

</body>
</html>
