<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>توسيط ذكي</title>
    
    <style>
        body {
 /* كودك السابق يبقى كما هو... */
    
    /* الأسطر السحرية لمنع التحديد والنسخ */
    -webkit-user-select: none; /* لمتصفحات سفاري وكروم القديمة */
    -ms-user-select: none;     /* لمتصفح إكسبلورر وإيدج */
    user-select: none;         /* الكود القياسي لجميع المتصفحات الحديثة */
            /* 1. السحر يبدأ هنا: نحول الـ body إلى شبكة ذكية */
            display: grid;
            
            /* 2. هذا السطر الواحد يضع كل شيء في المنتصف (أفقياً وعمودياً)! */
            place-items: center;
            
            /* 3. نعطي الصفحة ارتفاع الشاشة بالكامل */
            min-height: 100vh;
            margin: 0;
            background: linear-gradient(to bottom, #FFF1F4, #DE6B80);
            
/* لون خلفية خفيف لتوضيح الرؤية */
        }
.book-container {
            position: relative;
            width: 92vw;
            max-width: 600px;
            height:90vh;
            max-height: 90vh;
            perspective: 1500px;
            cursor: pointer;
        }

        .page {
overflow:hidden;
            position: absolute;
            top: 0; right: 0;
            width: 100%; height: 100%;
            background-color: #fdfaf6;    /* <-- الوضع الليلي يغير هذا فقط */
            border: 1px solid #c8d6e5;
            border-radius: 8px 0 0 8px;
            box-shadow: -5px 5px 15px rgba(0,0,0,0.4);
            transform-origin: right center;
            transition: transform 0.7s cubic-bezier(0.645, 0.045, 0.355, 1),
                        opacity 0.5s ease-in-out,
                        background-color 0.4s,
                        color 0.4s;
            transform-style: preserve-3d;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 5%;
            box-sizing: border-box;
            font-size: clamp(16px, 4vw, 22px);
            line-height: 1.8;
            color: #2f3640;
        }

        /* الوضع الليلي: فقط الصفحة وحروفها */
        
body.night .page {
            background-color: #1c2128;
            color: #cdd9e5;
            border-color: #30363d;
        }
        .page.flipped {
            transform: rotateY(180deg);
            opacity: 0;
            pointer-events: none;
        }

        .cover {
            background: linear-gradient(135deg, #1e3799, #0c2461);
            color: white;
            border: none;
            padding: 0;
            overflow: hidden;
        }
        .cover img {
            width: 100%; height: 100%;
            object-fit: cover;
            border-radius: inherit;
        }

        .page-number {
            position: absolute;
            bottom: 15px; left: 20px;
            font-size: 16px;
            color: #7f8fa6;
            font-weight: bold;
        }

        /* --- شريط أسفل --- */
        .bottom-bar {
            margin-top: 20px;
            color: #dcdde1;
            font-size: 15px;
            display: flex;
            width: 92vw;
            max-width: 600px;
            justify-content: space-between;
            align-items: center;
            padding: 0 10px;
            box-sizing: border-box;
        }

        /* زر الوضع الليلي */
        #btn-night {
            background: rgba(255,255,255,0.1);
            border: 1px solid rgba(255,255,255,0.2);
            color: #dcdde1;
            border-radius: 20px;
            padding: 4px 14px;
            font-size: 15px;
            cursor: pointer;
            transition: background 0.2s;
        }
        #btn-night:hover { background: rgba(255,255,255,0.2); }
#forbook{display:none;}
        #mune {
            /* نجعل النصوص (مثل الرابط) تتوسط الصندوق الخاص بها */
            text-align: center; 
        }

        .one {
           
            border: 0px;
            border-radius: 0px;
            padding: 15px; /* مسافة داخلية لكي يظهر اللون الأحمر حول الصورة */
        } 



        .forovero {
    position: relative; /* ضروري لعمل الـ absolute للابن */
    display: inline-block; /* يجعل الحاوية تأخذ حجم الصورة بالضبط وليس عرض الشاشة كله */
    
    /* هذا هو السطر الذي طلبته: يمنع الـ overlay من الخروج عن حدود الحاوية */
    overflow: hidden; 
    
    border-radius: 9px; /* اختيارياً: لقص الزوايا بشكل جميل */
}

.imageo {
    display: block; /* يزيل الفراغ الصغير الذي يظهر أحياناً تحت الصور */
    width: 200px;   /* حدد العرض الذي يناسبك */
    height: auto;
}


.overlay-boxo {
    position: absolute;
left:-120%;
top:160%;
    width: 300%; /* العرض الذي اخترته */
    height:7%; /* ارتفاع الشريط */
    background: rgba(255, 255, 255, 0.6); /* أبيض شفاف */
    transform: rotate(41.5deg);
    
    /* ربط الأنميشن */
    /* slide: اسم الحركة */
    /* 2s: سرعة الحركة (ثانيتان) */
    /* linear: سرعة ثابتة */
    /* infinite: التكرار لمالانهاية */
    animation: slide 1.5s linear infinite;
}

/* 2. تعريف حركة التكرار */
@keyframes slide {
    0% {
        top: 160%; /* يبدأ من أعلى الصورة بكثير */
        left: -500%;
    }
    1%{
        top: 160%; /* يبدأ من أعلى الصورة بكثير */
        left: -500%;
    }
    100% {
        top: 0%; /* ينتهي أسفل الصورة بكثير */
        left: 150%;
    }
}




.two {
           
            border: 0px;
            border-radius: 0px;
            padding: 15px; /* مسافة داخلية لكي يظهر اللون الأحمر حول الصورة */
        } 



        .forovert {
    position: relative; /* ضروري لعمل الـ absolute للابن */
    display: inline-block; /* يجعل الحاوية تأخذ حجم الصورة بالضبط وليس عرض الشاشة كله */
    
    /* هذا هو السطر الذي طلبته: يمنع الـ overlay من الخروج عن حدود الحاوية */
    overflow: hidden; 
    
    border-radius: 9px; /* اختيارياً: لقص الزوايا بشكل جميل */
}

.imaget {
    display: block; /* يزيل الفراغ الصغير الذي يظهر أحياناً تحت الصور */
    width: 200px;   /* حدد العرض الذي يناسبك */
    height: auto;
}


.overlay-boxt {
    position: absolute;
left:-120%;
top:160%;
    width: 300%; /* العرض الذي اخترته */
    height:7%; /* ارتفاع الشريط */
    background: rgba(255, 255, 255, 0.6); /* أبيض شفاف */
    transform: rotate(41.5deg);
    
    /* ربط الأنميشن */
    /* slide: اسم الحركة */
    /* 2s: سرعة الحركة (ثانيتان) */
    /* linear: سرعة ثابتة */
    /* infinite: التكرار لمالانهاية */
    animation: slide 1.5s linear infinite;
}

/* 2. تعريف حركة التكرار */
@keyframes slide {
    0% {
        top: 160%; /* يبدأ من أعلى الصورة بكثير */
        left: -500%;
    }
    1%{
        top: 200%; /* يبدأ من أعلى الصورة بكثير */
        left: -600%;
    }
    100% {
        top: 0%; /* ينتهي أسفل الصورة بكثير */
        left: 150%;
    }
}



.three {
           
            border: 0px;
            border-radius: 0px;
            padding: 15px; /* مسافة داخلية لكي يظهر اللون الأحمر حول الصورة */
        } 



        .foroverth {
    position: relative; /* ضروري لعمل الـ absolute للابن */
    display: inline-block; /* يجعل الحاوية تأخذ حجم الصورة بالضبط وليس عرض الشاشة كله */
    
    /* هذا هو السطر الذي طلبته: يمنع الـ overlay من الخروج عن حدود الحاوية */
    overflow: hidden; 
    
    border-radius: 9px; /* اختيارياً: لقص الزوايا بشكل جميل */
}

.imageth {
    display: block; /* يزيل الفراغ الصغير الذي يظهر أحياناً تحت الصور */
    width: 200px;   /* حدد العرض الذي يناسبك */
    height: auto;
}


.overlay-boxth {
    position: absolute;
left:-120%;
top:160%;
    width: 300%; /* العرض الذي اخترته */
    height:7%; /* ارتفاع الشريط */
    background: rgba(255, 255, 255, 0.6); /* أبيض شفاف */
    transform: rotate(41.5deg);
    
    /* ربط الأنميشن */
    /* slide: اسم الحركة */
    /* 2s: سرعة الحركة (ثانيتان) */
    /* linear: سرعة ثابتة */
    /* infinite: التكرار لمالانهاية */
    animation: slide 1.5s linear infinite;
}

/* 2. تعريف حركة التكرار */
@keyframes slide {
    0% {
        top: 160%; /* يبدأ من أعلى الصورة بكثير */
        left: -500%;
    }
    1%{
        top: 200%; /* يبدأ من أعلى الصورة بكثير */
        left: -600%;
    }
    100% {
        top: 0%; /* ينتهي أسفل الصورة بكثير */
        left: 150%;
    }
}
 .sharo{
  position: absolute;
  width: 65%; 
  height: 8%;
  left: -16%; 
  top: 6%; 
background: #00cc00;
transform:rotate(320deg);
font-size: 13px;
} 
#inka{display:none;}
#sharth{
background:#dddddd;
}
#shart{
background: #ff3300;}

#muneo {
    position: absolute;
    top: 3%;
    
    width: 100%;
    height: auto;
    
    /* 👈 السطر السحري للتوسيط الأفقي للنصوص والأزرار */
    text-align: center; 
}

h4 {
    /* 1. يجبر الكلمات الطويلة جداً على الانقسام والنزول للسطر التالي حتى لا تخرب التصميم */
    word-wrap: break-word;
    overflow-wrap: break-word;
    /* 2. (خطوة اختيارية ومهمة للمحترفين) تحديد أقصى عرض للنص */
    /* هذا يجعل النص ينزل لسطر جديد قبل أن يلتصق بحواف شاشة الهاتف تماماً */
    max-width: 90%; 
    /* 3. يحافظ على بقاء الصندوق في المنتصف بعد تحديد عرضه */
    margin: 0 auto; 
    /* 4. يضيف مسافة مريحة للعين بين الأسطر عندما ينزل النص لسطر جديد */
    line-height: 1.6; 
}



#munet {
    position: absolute;
    top: 3%;
    width: 100%;
    height: auto;
    /* 👈 السطر السحري للتوسيط الأفقي للنصوص والأزرار */
    text-align: center; 
}

#muneth {
    position: absolute;
    top: 3%;
    width: 100%;
    height: auto;
    /* 👈 السطر السحري للتوسيط الأفقي للنصوص والأزرار */
    text-align: center; 
}
#muneo{display:none;}
#munet{display:none;}
#muneth{display:none;}
#back1, #back2, #back3 {
    position:absolute;
    right:3%;
    top:2%;
}
#imageo #imaget #imageth{
    -webkit-user-drag: none;
    user-drag: none;
    
    /* هذا السطر يمنع المتصفح من التعرف على أي نقرة على الصورة تماماً! 
       مما يعني أن قائمة "حفظ الصورة" لن تظهر أبداً */
    pointer-events: none; 
}
#logo{
position: absolute; 
left:30%;top:1%;
width:35%;height:20%;
}
#forbook{display:none;}
.back{position: absolute;
top:2%; right:1%;}
    </style>  
</head>

<body>
    <div id="muneo">
<div id="info">
<h3 id="ino">معلومات قصیره عن قصه</h3>
<h4 id="naso">اكشن
تحقيق
جريمة
صداقة
غموض
لؤي
الضوء الذي كاد أن ينطفئ قد عاد فتيله للاشتعال.
 لكن بدل أن ينشر الدفء حوله، ترك صقيع قلبه يتفشى،

 فبعد فقدان ظله إلى الأبد، لم يعد قادرًا على ابتسام.



الحزء الثاني من رواية ظل بجوار الضوء، 

انصحك بقراءة جزء الاول اولا، حتى تتعرف على الشخصيات وعلاقاتهم.</h4>
<h4><a id="lio" href="https://www.wattpad.com/story/404670119-%D8%B8%D9%84-%D8%A8%D8%AC%D9%88%D8%A7%D8%B1-%D8%A7%D9%84%D8%B6%D9%88%D8%A1-_sanguis-_">لقرٲئة قصه بٲكمله زوروا هذا موقیع</a></h4>
<button id="back1" onclick="back()">➡رجوع</button> 
</div>
</div> 


<div id="munet">
<div id="infot">
<h3 id="int">معلومات قصیره عن قصه</h3>
<h4 id="nast">في عالم مبني على المشاعر، كان أنس مجرد محاكاة. عبقري في ارتداء الأقنعة، بارع في تزييف كل ابتسامة ودمعة. هو ظلٌ يعيش بين الناس، يدرسهم، ويحللهم دون أن يشعر بشيء.
  
  ولكن عندما يدخل "لؤي" إلى معادلته - ضوءٌ على وشك الانطفاء، روحٌ تقاتل من أجل كل نفس - يجد أنس نفسه أمام متغير لم يحسب له حساب. متغير يهدد بنسف نظامه بالكامل.
  
  .فماذا يحدث عندما يقرر الظل أن يقترب من الضوء ليس ليشعر بالدفء، بل ليدرس كيفية احتراقه؟ وهل يمكن لتجربة علمية باردة أن تتحول إلى شيء آخر... شيء أكثر خطورة على كليهما</h4>
<h4><a id="lit" href="https://www.wattpad.com/story/397079033-%D8%B8%D9%84%D9%8C-%D8%A8%D8%AC%D9%88%D8%A7%D8%B1-%D8%A7%D9%84%D8%B6%D9%88%D8%A1">لقرٲئة قصه بٲكمله زوروا هذا موقیع</a></h4>
<button id="back2" onclick="back()">➡رجوع</button> 
<button id="ksat"onclick="ksat()">لقرٲة هنا اضغط علی زر</button> 
</div>
</div>



<div id="muneth">
<div id="infoth">
<h3 id="inth">معلومات قصیره عن قصه</h3>
<h4 id="nasth">تخيل مكاناً لا يُصنّع الأدوية ولا الأسلحة، بل يصطنع "العقول". مختبر سري، مهمته الوحيدة إنتاج  العباقرة من أطفال بلا مأوى، ليتم بيعهم في "المزادات السوداء" لأماكن مسؤولة عن تجارب الممنوعة على البشر.

في رواية خاصة بآرثر! بعنوان " آرثر : غُبار النوابغ "

رواية جانبية ل(ظل بجوار الضوء)</h4>
<h4></h4>
<button id="back3" onclick="back()"> ➡رجوع</button> 
</div>
</div> 
    <div id="mune">
<img id="logo" src="https://i.ibb.co/fVYf0qP8/IMG-20260312-170324-691.jpg" alt="IMG-20260312-170324-691" border="0">
<br><br><br><br><br><br><br><br>
<label for="language" id="selec">اختر اللغة:</label>
<select id="language" onchange="updateTran()">
    <option value="0">العربية</option>
    <option value="1">English (الإنجليزية)</option>
    <option value="2">Français (الفرنسية)</option>
    <option value="3">Español (الإسبانية)</option>
    <option value="4">Deutsch (الألمانية)</option>
    <option value="5">Italiano (الإيطالية)</option>
    <option value="6">Türkçe (التركية)</option>
    <option value="7">فارسی (الفارسية)</option>
    <option value="8">Русский (الروسية)</option>
    <option value="9">中文 (الصينية)</option>
    <option value="10">日本語 (اليابانية)</option>
    <option value="11">한국어 (الكورية)</option>
    <option value="12">हिन्दी (الهندية)</option>
</select>
<p id="inka">القيمة الحالية لـ tran هي: <span id="display-tran"></span></p>

<br><br>



        <a id="link" href="https://www.wattpad.com/user/Scarlet2moon">صفحة كاتب</a> 
        <br><br><br><br>
    


        <div id="one" class="one">
    <h3>ظل بجوار ضوء 2</h3>

    <div class="forovero">
    <img onclick="moreo();more()"class="imageo" src="https://i.ibb.co/wF02vd5C/IMG-20260311-172025-198.jpg" alt="صورة">
    <div id="sharo"class="sharo">مستمر</div>
    <div class="overlay-boxo">
        
    </div>
    
    </div>

  <br> <button id="likeo" onclick="addVote('likeo', '👍')">👍 ...</button> 
       <button id="unlikeo" onclick="addVote('unlikeo', '👎')">👎 ...</button> 
        </div> 



<br><br><br><br>
 <div id="two" class="two">
    <h3>ظل بجوار ضوء </h3>

    <div class="forovert">
    <img onclick="moret();more()" class="imaget" src="https://i.ibb.co/Q3YJ0xyX/IMG-20260311-172025-704.jpg" alt="IMG 20260311 172025 704">
    <div id="shart"class="sharo">مكتمل</div>
    <div class="overlay-boxt">
        
    </div>
    </div>

  <br> <button id="liket" onclick="addVote('liket', '👍')">👍 ...</button> 
       <button id="unliket" onclick="addVote('unliket', '👎')">👎 ...</button> 
        </div> 




<br><br><br><br>
 <div id="three" class="three">
    <h3>غبار نوابغ   </h3>

    <div class="foroverth">
    <img class="imageth" onclick="moreth();more();"src="https://i.ibb.co/dsTgmW96/IMG-20260311-172025-763.jpg" alt="IMG 20260311 172025 704">
    <div id="sharth"class="sharo">قریباً</div>
    <div class="overlay-boxth">
        
    </div>
    </div>

  <br> <button id="liketh" onclick="addVote('liketh', '👍')">👍 ...</button> 
       <button id="unliketh" onclick="addVote('unliketh', '👎')">👎 ...</button> 
       
 </div> 

    </div>




<nav id="forbook">
<h1 id="namebook"></h1>
<div class="book-container" id="book">
    <div class="page cover" id="front-cover"></div>
    <div class="page cover" id="back-cover">
        <h3 style="margin-top:auto;margin-top:180px;">یتبع...</h3>
    <br><br><br><br><br><br><br><br>    <p ">©جمیع حقوق محفوظة</p>
        <p>الكاتبة Scarlet2moon</p>
    </div>
</div>

<div class="bottom-bar">
    <button id="btn-night">🌙</button>
</div>
<button id="backb2"class="back"onclick="bac()">➔</button> 
</nav>
</body>
    <script>
function bac(){
document.getElementById("forbook").style.display="none";
document.getElementById("mune").style.display="block"; 
} 
let tran = 0;
let tran1 = [
    "مستمر", "Ongoing", "En cours", "En curso", "Laufend", "In corso", "Devam ediyor", "در حال انتشار", "Продолжается", "连载中", "連載中", "연재중", "जारी है"
];
let tran2 = [
    "مكتمل", "Completed", "Terminé", "Finalizado", "Abgeschlossen", "Completato", "Tamamlandı", "پایان یافته", "Завершен", "已完结", "完結", "완결", "पूरा हुआ"
];

let tran3 = [
    "قريباً", "Coming Soon", "Bientôt", "Próximamente", "Demnächst", "Prossimamente", "Yakında", "به زودی", "Скоро", "即将推出", "近日公開", "곧 공개", "जल्द आ رہا ہے"
];

let tran5 = [
    "صفحة الكاتب", "Author Profile", "Page de l'auteur", "Perfil del autor", "Autorenprofil", "Profilo autore", "Yazar Profili", "صفحه نویسنده", "Профиль автора", "作者主页", "作者ページ", "작가 페이지", "लेखक प्रोफाइल"
];
let tran6 = [
    "اختر اللغة", "Select Language", "Choisir la langue", "Seleccionar idioma", "Sprache wählen", "Seleziona lingua", "Dil Seçin", "انتخاب زبان", "Выберите язык", "选择语言", "言語を選択", "언어 선택", "भाषा चुनें"
];
let tran7 = [
    "رجوع",        // 0: العربية
    "Back",        // 1: English (الإنجليزية)
    "Retour",      // 2: Français (الفرنسية)
    "Volver",      // 3: Español (الإسبانية)
    "Zurück",      // 4: Deutsch (الألمانية)
    "Indietro",    // 5: Italiano (الإيطالية)
    "Geri",        // 6: Türkçe (التركية)
    "بازگشت",      // 7: فارسی (الفارسية)
    "Назад",       // 8: Русский (الروسية)
    "返回",        // 9: 中文 (الصينية)
    "戻る",        // 10: 日本語 (اليابانية)
    "뒤로",        // 11: 한국어 (الكورية)
    "वापस"         // 12: हिन्दी (الهندية)
];

let tran8 = [
    "معلومات قصیره عن قصه",
    "Brief story info",
    "Brèves infos sur l'histoire",
    "Breve información de la historia",
    "Kurze Infos zur Geschichte",
    "Brevi info sulla storia",
    "Hikaye hakkında kısa bilgi",
    "اطلاعات کوتاه درباره داستان",
    "Краткая информация об истории",
    "关于故事的简短信息",
    "物語の短い情報",
    "이야기에 대한 짧은 정보",
    "कहानी के बारे में संक्षिप्त जानकारी"
];
let tran9 = [
    "لقرٲة قصه بٲكمله زوروا هذا موقیع",
    "To read the full story, visit this website",
    "Pour lire l'histoire complète, visitez ce site",
    "Para leer la historia completa, visita este sitio",
    "Um die ganze Geschichte zu lesen, besuchen Sie diese Website",
    "Per leggere la storia completa, visita questo sito",
    "Hikayenin tamamını okumak için bu siteyi ziyaret edin",
    "برای خواندن داستان کامل، از این سایت دیدن کنید",
    "Чтобы прочитать историю полностью, посетите этот сайт",
    "要阅读完整故事，请访问此网站",
    "物語の全編を読むには、このサイトにアクセスしてください",
    "전체 이야기를 읽으려면 이 웹사이트를 방문하세요",
    "पूरी कहानी पढ़ने के लिए, इस वेबसाइट पर जाएँ"
];

let tran10 = [
    "اكشن تحقيق جريمة صداقة غموض لؤي الضوء الذي كاد أن ينطفئ قد عاد فتيله للاشتعال. لكن بدل أن ينشر الدفء حوله، ترك صقيع قلبه يتفشى، فبعد فقدان ظله إلى الأبد، لم يعد قادرًا على ابتسام. الحزء الثاني من رواية ظل بجوار الضوء، انصحك بقراءة جزء الاول اولا، حتى تتعرف على الشخصيات وعلاقاتهم.",
    "Action, investigation, crime, friendship, mystery. Luay: The light that almost went out has been reignited. But instead of spreading warmth around him, he let the frost of his heart spread; after losing his shadow forever, he is no longer able to smile. The second part of the novel 'A Shadow Next to the Light'. I advise you to read the first part first to understand the characters and their relationships.",
    "Action, enquête, crime, amitié, mystère. Luay : La lumière qui a failli s'éteindre s'est rallumée. Mais au lieu de répandre la chaleur autour de lui, il a laissé le givre de son cœur se propager ; après avoir perdu son ombre pour toujours, il n'est plus capable de sourire. La deuxième partie du roman 'Une ombre près de la lumière'. Je vous conseille de lire la première partie d'abord, afin de connaître les personnages et leurs relations.",
    "Acción, investigación, crimen, amistad, misterio. Luay: La luz que casi se apaga ha vuelto a encenderse. Pero en lugar de esparcir calor a su alrededor, dejó que la escarcha de su corazón se extendiera; después de perder su sombra para siempre, ya no es capaz de sonreír. La segunda parte de la novela 'Una sombra junto a la luz'. Te aconsejo leer la primera parte primero, para que conozcas a los personajes y sus relaciones.",
    "Aktion, Ermittlung, Verbrechen, Freundschaft, Geheimnis. Luay: Das Licht, das fast erloschen war, wurde wieder entfacht. Doch anstatt Wärme um sich zu verbreiten, ließ er den Frost seines Herzens sich ausbreiten; nachdem er seinen Schatten für immer verloren hat, kann er nicht mehr lächeln. Der zweite Teil des Romans 'Ein Schatten neben dem Licht'. Ich rate dir, zuerst den ersten Teil zu lesen, damit du die Charaktere und ihre Beziehungen kennenlernst.",
    "Azione, indagine, crimine, amicizia, mistero. Luay: La luce che stava per spegnersi si è riaccesa. Ma invece di diffondere calore intorno a sé, ha lasciato che il gelo del suo cuore si diffondesse; dopo aver perso per sempre la sua ombra, non è più in grado di sorridere. La seconda parte del romanzo 'Un'ombra accanto alla luce'. Ti consiglio di leggere prima la prima parte, per conoscere i personaggi e le loro relazioni.",
    "Aksiyon, soruşturma, suç, dostluk, gizem. Luay: Neredeyse sönmek üzere olan ışık yeniden alevlendi. Ancak etrafına sıcaklık yaymak yerine, kalbindeki buzun yayılmasına izin verdi; gölgesini sonsuza dek kaybettikten sonra artık gülümseyemez oldu. 'Işığın Yanındaki Gölge' romanının ikinci bölümü. Karakterleri ve ilişkilerini tanımak için önce ilk bölümü okumanızı tavsiye ederim.",
    "اکشن، تحقیق، جنایت، دوستی، رازآلود. لؤی: نوری که نزدیک بود خاموش شود، دوباره شعله‌ور شد. اما به جای اینکه گرما را در اطرافش پخش کند، اجازه داد سرمای قلبش گسترش یابد؛ چرا که پس از از دست دادن سایه‌اش برای همیشه، دیگر قادر به لبخند زدن نیست. قسمت دوم رمان «سایه‌ای در کنار نور». پیشنهاد می‌کنم ابتدا قسمت اول را بخوانید تا با شخصیت‌ها و روابطشان آشنا شوید.",
    "Экшен, расследование, преступление, дружба, мистика. Луай: Свет, который почти погас, снова вспыхнул. Но вместо того, чтобы распространять тепло вокруг себя, он позволил стуже своего сердца распространиться; навсегда потеряв свою тень, он больше не может улыбаться. Вторая часть романа «Тень рядом со светом». Советую вам сначала прочитать первую часть, чтобы познакомиться с персонажами и их отношениями.",
    "动作，调查，犯罪，友谊，悬疑。Luay：那盏几乎熄灭的灯又重新点燃了。但他没有向周围散发温暖，而是任由内心的冰霜蔓延；在永远失去影子之后，他再也无法微笑。《光芒旁的阴影》小说的第二部。建议您先阅读第一部，以便了解角色及其关系。",
    "アクション、捜査、犯罪、友情、ミステリー。ルアイ：消えかかっていた光が再び灯った。しかし、周囲に暖かさを広げる代わりに、彼は心の霜を広げた。永遠に影を失った後、彼はもはや微笑むことができない。小説『光のそばの影』の第2部。キャラクターとその関係性を知るために、まず第1部を読むことをお勧めします。",
    "액션, 수사, 범죄, 우정, 미스터리. 루아이: 거의 꺼질 뻔했던 빛이 다시 타올랐습니다. 하지만 주위에 따뜻함을 퍼뜨리는 대신, 그는 마음의 서리가 퍼지게 내버려 두었습니다. 그림자를 영원히 잃은 후, 그는 더 이상 웃을 수 없게 되었습니다. 소설 '빛 옆의 그림자' 제2부. 캐릭터와 그들의 관계를 알기 위해 먼저 1부를 읽는 것을 권장합니다.",
    "एक्शन, जांच, अपराध, दोस्ती, रहस्य। लुए: वह रोशनी जो लगभग बुझ चुकी थी, फिर से जल उठी है। लेकिन अपने चारों ओर गर्मी फैलाने के बजाय, उसने अपने दिल की ठंडक को फैलने दिया; अपनी परछाई को हमेशा के लिए खो देने के बाद, वह अब मुस्कुराने में सक्षम नहीं है। उपन्यास 'रोशनी के बगल में एक परछाई' का दूसरा भाग। मेरा सुझाव है कि आप पात्रों और उनके रिश्तों को जानने के लिए पहले पहला भाग पढ़ें।"
];

let tran11 = [
    "في عالم مبني على المشاعر، كان أنس مجرد محاكاة. عبقري في ارتداء الأقنعة، بارع في تزييف كل ابتسامة ودمعة. هو ظلٌ يعيش بين الناس، يدرسهم، ويحللهم دون أن يشعر بشيء. ولكن عندما يدخل \"لؤي\" إلى معادلته - ضوءٌ على وشك الانطفاء، روحٌ تقاتل من أجل كل نفس - يجد أنس نفسه أمام متغير لم يحسب له حساب. متغير يهدد بنسف نظامه بالكامل. فماذا يحدث عندما يقرر الظل أن يقترب من الضوء ليس ليشعر بالدفء، بل ليدرس كيفية احتراقه؟ وهل يمكن لتجربة علمية باردة أن تتحول إلى شيء آخر... شيء أكثر خطورة على كليهما",
    "In a world built on emotions, Anas was merely a simulation. A genius at wearing masks, a master at faking every smile and tear. He is a shadow living among people, studying and analyzing them without feeling a thing. But when \"Luay\" enters his equation—a light on the verge of going out, a soul fighting for every breath—Anas finds himself facing an uncalculated variable. A variable that threatens to completely shatter his system. What happens when the shadow decides to approach the light, not to feel its warmth, but to study how it burns? And can a cold scientific experiment turn into something else... something far more dangerous for both of them?",
    "Dans un monde bâti sur les émotions, Anas n'était qu'une simulation. Un génie pour porter des masques, passé maître dans l'art de simuler chaque sourire et chaque larme. Il est une ombre vivant parmi les gens, les étudiant et les analysant sans rien ressentir. Mais lorsque \"Luay\" entre dans son équation — une lumière sur le point de s'éteindre, une âme se battant pour chaque souffle — Anas se retrouve face à une variable imprévue. Une variable qui menace de détruire complètement son système. Que se passe-t-il lorsque l'ombre décide de s'approcher de la lumière, non pas pour ressentir sa chaleur, mais pour étudier comment elle se consume ? Et une froide expérience scientifique peut-elle se transformer en autre chose... quelque chose de bien plus dangereux pour eux deux ?",
    "En un mundo construido sobre emociones, Anas era solo una simulación. Un genio usando máscaras, experto en fingir cada sonrisa y lágrima. Es una sombra que vive entre la gente, estudiándolos y analizándolos sin sentir nada. Pero cuando \"Luay\" entra en su ecuación —una luz a punto de apagarse, un alma luchando por cada aliento— Anas se encuentra ante una variable incalculable. Una variable que amenaza con destruir todo su sistema. ¿Qué sucede cuando la sombra decide acercarse a la luz no para sentir su calor, sino para estudiar cómo se consume? ¿Y puede un frío experimento científico convertirse en algo más... algo mucho más peligroso para ambos?",
    "In einer Welt, die auf Emotionen aufbaut, war Anas nur eine Simulation. Ein Genie im Tragen von Masken, ein Meister im Vortäuschen von jedem Lächeln und jeder Träne. Er ist ein Schatten, der unter Menschen lebt, sie studiert und analysiert, ohne etwas zu fühlen. Doch als \"Luay\" in seine Gleichung tritt – ein Licht, das kurz vor dem Erlöschen steht, eine Seele, die um jeden Atemzug kämpft – steht Anas vor einer unberechenbaren Variablen. Einer Variablen, die sein gesamtes System zu zerstören droht. Was passiert, wenn der Schatten beschließt, sich dem Licht zu nähern, nicht um seine Wärme zu spüren, sondern um zu studieren, wie es verbrennt? Und kann sich ein kaltes wissenschaftliches Experiment in etwas anderes verwandeln... etwas viel Gefährlicheres für beide?",
    "In un mondo basato sulle emozioni, Anas non era altro che una simulazione. Un genio nell'indossare maschere, abile nel fingere ogni sorriso e ogni lacrima. È un'ombra che vive tra le persone, studiandole e analizzandole senza provare nulla. Ma quando \"Luay\" entra nella sua equazione — una luce sul punto di spegnersi, un'anima che combatte per ogni respiro — Anas si trova di fronte a una variabile imprevista. Una variabile che minaccia di distruggere completamente il suo sistema. Cosa succede quando l'ombra decide di avvicinarsi alla luce non per sentire il suo calore, ma per studiare come brucia? E può un freddo esperimento scientifico trasformarsi in qualcos'altro... qualcosa di molto più pericoloso per entrambi?",
    "Duygular üzerine kurulu bir dünyada Anas sadece bir simülasyondu. Maske takmada bir dahi, her gülümsemeyi ve gözyaşını sahteleştirmede bir usta. O, insanlar arasında yaşayan, onları hiçbir şey hissetmeden inceleyen ve analiz eden bir gölgedir. Ancak \"Luay\" onun denklemine girdiğinde - sönmek üzere olan bir ışık, her nefes için savaşan bir ruh - Anas kendini hesaplanmamış bir değişkenin önünde bulur. Tüm sistemini yok etmekle tehdit eden bir değişken. Gölge, ışığa sıcaklığını hissetmek için değil, nasıl yandığını incelemek için yaklaşmaya karar verdiğinde ne olur? Ve soğuk bir bilimsel deney başka bir şeye... ikisi için de çok daha tehlikeli bir şeye dönüşebilir mi?",
    "در دنیایی که بر پایه احساسات بنا شده است، انس تنها یک شبیه‌سازی بود. نابغه‌ای در استفاده از نقاب‌ها، استاد در جعل هر لبخند و قطره اشک. او سایه‌ای است که در میان مردم زندگی می‌کند، بدون اینکه چیزی احساس کند آنها را مطالعه و تحلیل می‌کند. اما وقتی «لؤی» وارد معادله او می‌شود - نوری در آستانه خاموشی، روحی که برای هر نفس می‌جنگد - انس خود را در برابر متغیری محاسبه نشده می‌یابد. متغیری که تهدید می‌کند کل سیستم او را نابود سازد. چه اتفاقی می‌افتد وقتی سایه تصمیم می‌گیرد به نور نزدیک شود، نه برای احساس گرمای آن، بلکه برای بررسی نحوه سوختنش؟ و آیا یک آزمایش علمی سرد می‌تواند به چیز دیگری تبدیل شود... چیزی بسیار خطرناک‌تر برای هر دوی آنها؟",
    "В мире, построенном на эмоциях, Анас был всего лишь симуляцией. Гений в ношении масок, мастер в подделке каждой улыбки и слезы. Он — тень, живущая среди людей, изучающая и анализирующая их, ничего не чувствуя. Но когда в его уравнение входит «Луай» — свет, готовый погаснуть, душа, сражающаяся за каждый вдох, — Анас оказывается перед неучтенной переменной. Переменной, которая грозит полностью разрушить его систему. Что происходит, когда тень решает приблизиться к свету не для того, чтобы почувствовать его тепло, а чтобы изучить, как он горит? И может ли холодный научный эксперимент превратиться во что-то другое... во что-то гораздо более опасное для них обоих?",
    "在一个建立在情感之上的世界里，阿纳斯仅仅是一个模拟。一个戴面具的天才，擅长伪装每一个微笑和泪水。他是一个生活在人群中的影子，研究并分析他们，却没有任何感觉。但是当“卢埃”进入他的方程式——一盏即将熄灭的灯，一个为每一次呼吸而战的灵魂——阿纳斯发现自己面临一个未曾计算的变量。这个变量威胁要彻底摧毁他的系统。当影子决定靠近光，不是为了感受它的温暖，而是为了研究它是如何燃烧的，会发生什么？一个冰冷的科学实验能变成别的什么吗……对他们两人来说都更危险的东西？",
    "感情で構築された世界で、アナスは単なるシミュレーションに過ぎなかった。仮面を被る天才であり、すべての笑顔と涙を偽る達人。彼は人々の間に生きる影であり、何も感じることなく彼らを研究し分析している。しかし、「ルアイ」が彼の方程式に入り込んだとき――消えかかっている光、一呼吸ごとに戦う魂――アナスは計算外の変数に直面する。彼のシステム全体を完全に破壊する恐れのある変数。影が光の暖かさを感じるためではなく、それがどのように燃えるかを研究するために光に近づくことを決意したとき、何が起こるのか？そして、冷たい科学実験は別の何かに…二人にとってさらに危険な何かに変わることができるのだろうか？",
    "감정을 바탕으로 세워진 세상에서 아나스는 단순한 시뮬레이션에 불과했다. 가면을 쓰는 천재, 모든 미소와 눈물을 위조하는 달인. 그는 사람들 사이에 사는 그림자로, 아무것도 느끼지 못한 채 그들을 연구하고 분석한다. 하지만 \"루아이\"가 그의 방정식에 들어왔을 때 - 꺼지기 직전의 빛, 매 호흡을 위해 싸우는 영혼 - 아나스는 계산되지 않은 변수 앞에 놓인 자신을 발견한다. 그의 시스템 전체를 완전히 파괴할 위험이 있는 변수. 그림자가 빛의 따뜻함을 느끼기 위해서가 아니라 빛이 어떻게 타오르는지 연구하기 위해 빛에 다가가기로 결심하면 어떤 일이 벌어질까? 그리고 차가운 과학 실험이 다른 무언가로... 두 사람 모두에게 훨씬 더 위험한 무언가로 변할 수 있을까?",
    "भावनाओं पर बनी दुनिया में, अनस केवल एक अनुकरण था। मुखौटे पहनने में एक प्रतिभाशाली, हर मुस्कान और आंसू को नकली बनाने में माहिर। वह लोगों के बीच रहने वाली एक परछाई है, जो बिना कुछ महसूस किए उनका अध्ययन और विश्लेषण करता है। लेकिन जब \"लुए\" उसके समीकरण में प्रवेश करता है - एक रोशनी जो बुझने के कगार पर है, एक आत्मा जो हर सांस के लिए लड़ रही है - अनस खुद को एक अकल्पनीय चर के सामने पाता है। एक ऐसा चर जो उसके पूरे सिस्टम को पूरी तरह से नष्ट करने की धमकी देता है। क्या होता है जब परछाई रोशनी के करीब जाने का फैसला करती है, उसकी गर्मी को महसूस करने के लिए नहीं, बल्कि यह अध्ययन करने के लिए कि यह कैसे जलती है? और क्या एक ठंडा वैज्ञानिक प्रयोग किसी और चीज़ में बदल सकता है... किसी ऐसी चीज़ में जो उन दोनों के लिए बहुत अधिक खतरनाक हो?"
];
let tran12 = [
    "تخيل مكاناً لا يُصنّع الأدوية ولا الأسلحة، بل يصطنع \"العقول\". مختبر سري، مهمته الوحيدة إنتاج العباقرة من أطفال بلا مأوى، ليتم بيعهم في \"المزادات السوداء\" لأماكن مسؤولة عن تجارب الممنوعة على البشر. في رواية خاصة بآرثر! بعنوان \" آرثر : غُبار النوابغ \" رواية جانبية ل(ظل بجوار الضوء)",
    "Imagine a place that manufactures neither drugs nor weapons, but rather \"minds\". A secret laboratory whose sole mission is to produce geniuses from homeless children, only to be sold in \"black auctions\" to places responsible for forbidden human experiments. In a special novel for Arthur! Titled \"Arthur: Dust of Geniuses\", a spin-off of (A Shadow Next to the Light).",
    "Imaginez un endroit qui ne fabrique ni médicaments ni armes, mais qui crée des \"esprits\". Un laboratoire secret dont l'unique mission est de produire des génies à partir d'enfants sans abri, pour les vendre dans des \"enchères noires\" à des lieux responsables d'expériences humaines interdites. Dans un roman spécial pour Arthur ! Intitulé \"Arthur : La Poussière des Génies\", un spin-off de (Une Ombre Près de la Lumière).",
    "Imagina un lugar que no fabrica medicamentos ni armas, sino que crea \"mentes\". Un laboratorio secreto cuya única misión es producir genios a partir de niños sin hogar, para ser vendidos en \"subastas negras\" a lugares responsables de experimentos humanos prohibidos. ¡En una novela especial para Arthur! Titulada \"Arthur: Polvo de Genios\", un spin-off de (Una sombra junto a la luz).",
    "Stell dir einen Ort vor, der weder Medikamente noch Waffen herstellt, sondern \"Verstand\" erschafft. Ein geheimes Labor, dessen einzige Mission es ist, aus obdachlosen Kindern Genies zu machen, um sie in \"schwarzen Auktionen\" an Orte zu verkaufen, die für verbotene Menschenversuche verantwortlich sind. In einem speziellen Roman für Arthur! Mit dem Titel \"Arthur: Staub der Genies\", ein Spin-off von (Ein Schatten neben dem Licht).",
    "Immagina un luogo che non produce né medicine né armi, ma crea \"menti\". Un laboratorio segreto la cui unica missione è produrre geni da bambini senzatetto, per essere venduti in \"aste nere\" a luoghi responsabili di esperimenti umani proibiti. In un romanzo speciale per Arthur! Intitolato \"Arthur: Polvere di Geni\", uno spin-off di (Un'ombra accanto alla luce).",
    "İlaç ya da silah değil, \"zihinler\" üreten bir yer hayal edin. Tek görevi evsiz çocuklardan dahiler üretmek ve onları yasaklı insan deneylerinden sorumlu yerlere \"kara müzayedelerde\" satmak olan gizli bir laboratuvar. Arthur için özel bir romanda! \"Arthur: Dahilerin Tozu\" başlıklı, (Işığın Yanındaki Gölge) romanının bir yan ürünü.",
    "مکانی را تصور کنید که نه دارو می‌سازد و نه سلاح، بلکه \"ذهن‌ها\" را خلق می‌کند. یک آزمایشگاه مخفی که تنها مأموریتش تولید نوابغ از کودکان بی‌خانمان است تا در \"مزایده‌های سیاه\" به مکان‌هایی که مسئول آزمایش‌های ممنوعه انسانی هستند فروخته شوند. در یک رمان ویژه برای آرتور! با عنوان \"آرتور: غبار نوابغ\"، یک داستان فرعی از (سایه‌ای در کنار نور).",
    "Представьте себе место, где не производят ни лекарств, ни оружия, а создают «умы». Секретная лаборатория, чья единственная миссия — делать гениев из бездомных детей, чтобы продавать их на «черных аукционах» в места, ответственные за запрещенные эксперименты над людьми. В специальном романе об Артуре! Под названием «Артур: Пыль гениев», спин-офф (Тень рядом со светом).",
    "想象一个既不制造药物也不制造武器，而是制造“头脑”的地方。一个秘密实验室，其唯一任务是用无家可归的孩子培养天才，然后在“黑市拍卖”中卖给负责违禁人体实验的机构。在亚瑟的特别小说中！名为《亚瑟：天才之尘》，是《光芒旁的阴影》的衍生作品。",
    "薬や武器ではなく、「頭脳」を作り出す場所を想像してみてほしい。ホームレスの子供たちから天才を生み出し、禁じられた人体実験を行う施設に「闇オークション」で売ることを唯一の使命とする秘密の研究所。アーサーの特別小説で！『アーサー：天才たちの塵』と題された、『光のそばの影』のスピンオフ作品。",
    "약이나 무기가 아니라 \"두뇌\"를 만들어내는 곳을 상상해 보세요. 집 없는 아이들로 천재를 만들어 금지된 인체 실험을 담당하는 곳에 \"암시장 경매\"로 파는 것을 유일한 임무로 삼는 비밀 연구소. 아서를 위한 특별한 소설에서! '빛 옆의 그림자'의 스핀오프인 '아서: 천재들의 먼지'라는 제목의 소설입니다.",
    "एक ऐसी जगह की कल्पना करें जो न तो दवाइयां बनाती है और न ही हथियार, बल्कि \"दिमाग\" बनाती है। एक गुप्त प्रयोगशाला जिसका एकमात्र मिशन बेघर बच्चों से प्रतिभा पैदा करना है, ताकि उन्हें निषिद्ध मानव प्रयोगों के लिए जिम्मेदार जगहों पर \"काली नीलामी\" में बेचा जा सके। आर्थर के लिए एक विशेष उपन्यास में! जिसका शीर्षक है \"आर्थर: डस्ट ऑफ जीनियस\", जो (ए शैडो नेक्स्ट टू द लाइट) का स्पिन-ऑफ़ है।"
];

function updateTran() {
    const list = document.getElementById("language");
    tran = Number(list.value);
    document.getElementById("display-tran").innerText = tran;
    
    document.getElementById("sharo").innerText=tran1[tran]; 
    document.getElementById("shart").innerText=tran2[tran]; 
    document.getElementById("sharth").innerText=tran3[tran];  
    document.getElementById("link").innerText=tran5[tran]; 
    document.getElementById("selec").innerText=tran6[tran]; 
    document.getElementById("back1").innerText=tran7[tran]+" ➡"; 
    document.getElementById("back2").innerText=tran7[tran]+" ➡"; 
    document.getElementById("back3").innerText=tran7[tran]+" ➡"; 
    document.getElementById("ino").innerText=tran8[tran]; 
    document.getElementById("int").innerText=tran8[tran]; 
    document.getElementById("inth").innerText=tran8[tran]; 
    document.getElementById("lio").innerText=tran9[tran]; 
    document.getElementById("lit").innerText=tran9[tran]; 
    document.getElementById("naso").innerText=tran10[tran]; 
    document.getElementById("nast").innerText=tran11[tran]; 
    document.getElementById("nasth").innerText=tran12[tran]; 
}
function more(){
document.getElementById("mune").style.display="none"; 
} 
function moreo(){
document.getElementById("muneo").style.display="block"; 
} 
function moret(){
document.getElementById("munet").style.display="block"; 
} 
function moreth(){
document.getElementById("muneth").style.display="block"; 
} 
function back(){
document.getElementById("mune").style.display="block"; 
document.getElementById("muneo").style.display="none";
document.getElementById("munet").style.display="none";
document.getElementById("muneth").style.display="none"; 
} 
// منع زر الفأرة الأيمن (الكليك يمين)
document.addEventListener('contextmenu', event => event.preventDefault());

// منع اختصارات لوحة المفاتيح المخصصة للمطورين
document.onkeydown = function(e) {
    // منع زر F12
    if(e.keyCode == 123) { 
        return false; 
    } 
    // Ctrl+Shift+I (فتح أدوات المطور)
    if(e.ctrlKey && e.shiftKey && e.keyCode == 'I'.charCodeAt(0)) { 
        return false; 
    } 
    // Ctrl+Shift+J (فتح وحدة التحكم)
    if(e.ctrlKey && e.shiftKey && e.keyCode == 'J'.charCodeAt(0)) { 
        return false; 
    } 
    // Ctrl+U (عرض مصدر الصفحة)
    if(e.ctrlKey && e.keyCode == 'U'.charCodeAt(0)) { 
        return false; 
    } 
}


let aghlifah = [
    `https://i.ibb.co/Q3YJ0xyX/IMG-20260311-172025-704.jpg`
];


let currentBookIndex = 0;

function ksat(){
document.getElementById("munet").style.display="none";
document.getElementById("forbook").style.display="block"; 
currentBookIndex = 0;
} 



// الكتاب يُبنى من Firebase - انظر script module أدناه
    </script>





        <script type="module">
      import { initializeApp } from "https://www.gstatic.com/firebasejs/12.10.0/firebase-app.js";
      import { getFirestore, doc, getDoc, onSnapshot, setDoc, updateDoc, increment } from "https://www.gstatic.com/firebasejs/12.10.0/firebase-firestore.js";

      // إعدادات مشروعك
      const firebaseConfig = {
        apiKey: "AIzaSyAUVDgbFlOgXNUc_98WI4PkMwFyrzx55_s",
        authDomain: "storypondy.firebaseapp.com",
        projectId: "storypondy",
        storageBucket: "storypondy.firebasestorage.app",
        messagingSenderId: "348159248678",
        appId: "1:348159248678:web:fddb9f82aeb16537c999e7",
        measurementId: "G-DW8KGJV4MJ"
      };

const nightBtn = document.getElementById('btn-night');
let isNight = localStorage.getItem('sp_night') === '1';
function applyNight() {
    document.body.classList.toggle('night', isNight);
    nightBtn.textContent = isNight ? '☀️' : '🌙';
}
applyNight();
nightBtn.addEventListener('click', () => {
    isNight = !isNight;
    localStorage.setItem('sp_night', isNight ? '1' : '0');
    applyNight();
});

      const app = initializeApp(firebaseConfig);
      const db = getFirestore(app);
      const likesRef = doc(db, "posts", "all_likes");

      // ===== جلب النص من Firebase وبناء الكتاب =====
      async function loadBook(index) {
          // جلب document اسمه book_0 أو book_1 إلخ
          const snap = await getDoc(doc(db, "books", "book_" + index));
          if (!snap.exists()) { console.error("لم يُوجد الكتاب في Firebase"); return; }
          
          const bookText = snap.data().text;
          
          // وضع صورة الغلاف (من المصفوفة المحلية)
          document.querySelector("#front-cover").innerHTML =
              `<img src="${aghlifah[index]}" alt="غلاف">`;

          // بناء الصفحات
          const WORDS_PER_PAGE = 115;
          const words = bookText.trim().split(/\s+/);
          const backCover = document.getElementById("back-cover");

          // احذف أي صفحات قديمة (عند تبديل الكتاب)
          document.querySelectorAll(".page:not(.cover)").forEach(p => p.remove());

          let chunks = [];
          for (let i = 0; i < words.length; i += WORDS_PER_PAGE) {
              const chunk = words.slice(i, i + WORDS_PER_PAGE).join(" ");
              chunks.push(`<div class="page"><p>${chunk}</p></div>`);
          }
          backCover.insertAdjacentHTML("beforebegin", chunks.join(""));

          // ترتيب الطبقات وأرقام الصفحات
          const pages = document.querySelectorAll(".page");
          let currentPage = 0;
          pages.forEach((page, i) => {
              page.style.zIndex = pages.length - i;
              if (i > 0 && i < pages.length - 1) {
                  const num = document.createElement("div");
                  num.className = "page-number";
                  num.innerText = i;
                  page.appendChild(num);
              }
          });

          // استعادة آخر صفحة
          const saveKey = "sp_page_" + index;
          const saved = parseInt(localStorage.getItem(saveKey) || "0");
          if (saved > 0 && saved < pages.length) {
              for (let i = 0; i < saved; i++) pages[i].classList.add("flipped");
              currentPage = saved;
          }

          function savePage() { localStorage.setItem(saveKey, currentPage); }

          // التقليب
          const book = document.getElementById("book");
          // احذف listener القديم بإعادة clone
          const newBook = book.cloneNode(true);
          book.parentNode.replaceChild(newBook, book);

          newBook.addEventListener("click", function(e) {
              const rect = this.getBoundingClientRect();
              const allPages = document.querySelectorAll(".page");
              if (e.clientX - rect.left < rect.width / 2) {
                  if (currentPage < allPages.length - 1) {
                      allPages[currentPage].classList.add("flipped");
                      currentPage++;
                      savePage();
                  }
              } else {
                  if (currentPage > 0) {
                      currentPage--;
                      allPages[currentPage].classList.remove("flipped");
                      savePage();
                  }
              }
          });
      }

      // استدعاء الكتاب حسب currentBookIndex
      loadBook(currentBookIndex);

      // كذلك عند الضغط على زر القراءة
      const _origKsat = window.ksat;
      window.ksat = function() {
          document.getElementById("munet").style.display = "none";
          document.getElementById("forbook").style.display = "block";
          currentBookIndex = 0;
          loadBook(currentBookIndex);
      };

      // دالة لتلوين الأزرار باللون الأزرق حسب تصويت المستخدم المحفوظ في جهازه
      function updateColors() {
          // المجموعات الثلاث لقصصك (o, t, th)
          ['o', 't', 'th'].forEach(group => {
              // جلب تصويت الزائر من ذاكرة هاتفه
              let vote = localStorage.getItem('vote_' + group);
              
              // إذا كان مصوت إعجاب، لون زر الإعجاب أزرق، وإلا اتركه عادياً
              document.getElementById('like' + group).style.background= (vote === 'like') ? '#007bff' : '';
              
              // إذا كان مصوت لم يعجبني، لون زر لم يعجبني أزرق، وإلا اتركه عادياً
              document.getElementById('unlike' + group).style.background= (vote === 'unlike') ? '#007bff' : '';
          });
      }

      // المراقبة الحية للأرقام
      onSnapshot(likesRef, (docSnap) => {
          if (docSnap.exists()) {
              const data = docSnap.data();
              document.getElementById("likeo").innerText = "👍 " + (data.likeo || 0);
              document.getElementById("unlikeo").innerText = "👎 " + (data.unlikeo || 0);
              document.getElementById("liket").innerText = "👍 " + (data.liket || 0);
              document.getElementById("unliket").innerText = "👎 " + (data.unliket || 0);
              document.getElementById("liketh").innerText = "👍 " + (data.liketh || 0);
              document.getElementById("unliketh").innerText = "👎 " + (data.unliketh || 0);
              
              // تحديث ألوان الأزرار لكي لا تختفي عند تحديث الصفحة
              updateColors(); 
          } else {
              setDoc(likesRef, {
                  likeo: 0, unlikeo: 0,
                  liket: 0, unliket: 0,
                  liketh: 0, unliketh: 0
              });
          }
      });

      // الدالة الذكية للإعجاب وإلغاء الإعجاب
      window.addVote = async function(buttonId, emoji) {
          // تحليل الزر لمعرفة هل هو إعجاب أم لا، ولأي قصة يتبع
          let isLike = buttonId.startsWith("like");
          let group = isLike ? buttonId.replace("like", "") : buttonId.replace("unlike", "");
          let type = isLike ? "like" : "unlike";
          let oppositeType = isLike ? "unlike" : "like";
          let oppositeBtnId = oppositeType + group;

          // جلب التصويت الحالي من ذاكرة المتصفح
          let currentVote = localStorage.getItem("vote_" + group);
          let updates = {};

          if (currentVote === type) {
              // الحالة 1: المستخدم ضغط على نفس الزر مرة أخرى (إلغاء التصويت)
              updates[buttonId] = increment(-1); // إنقاص الرقم من فايربيز
              localStorage.removeItem("vote_" + group); // حذف التصويت من جهازه
          } else if (currentVote === oppositeType) {
              // الحالة 2: المستخدم غير رأيه (من إعجاب إلى لم يعجبني أو العكس)
              updates[buttonId] = increment(1); // زيادة للزر الجديد
              updates[oppositeBtnId] = increment(-1); // إنقاص من الزر القديم
              localStorage.setItem("vote_" + group, type); // تحديث اختياره في جهازه
          } else {
              // الحالة 3: تصويت جديد لأول مرة
              updates[buttonId] = increment(1); 
              localStorage.setItem("vote_" + group, type);
          }

          // تلوين الأزرار فوراً حسب التحديث الجديد
          updateColors();

          // إرسال التغييرات إلى فايربيز
          await updateDoc(likesRef, updates);
      };

    </script>


</body>
</html>
