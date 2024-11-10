## Hi there 👋

<!--
**ArtemH2004/ArtemH2004** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="./assets/css/style.css">
    <title>Castaway</title>
    <style>
@font-face {
    font-family: 'DMSans';
    src: url('../fonts/DMSans-Regular.woff2') format('woff2');
    font-weight: 400;
    font-style: normal;
    font-display: swap;
}


/**
  Нормализация блочной модели
 */
 *,
 *::before,
 *::after {
   box-sizing: border-box;
 }
 
 /**
   Убираем внутренние отступы слева тегам списков,
   у которых есть атрибут class
  */
 :where(ul, ol):where([class]) {
   padding-left: 0;
 }
 
 /**
   Убираем внешние отступы body и двум другим тегам,
   у которых есть атрибут class
  */
 body,
 :where(blockquote, figure):where([class]) {
   margin: 0;
 }
 
 /**
   Убираем внешние отступы вертикали нужным тегам,
   у которых есть атрибут class
  */
 :where(
   h1,
   h2,
   h3,
   h4,
   h5,
   h6,
   p,
   ul,
   ol,
   dl
 ):where([class]) {
   margin-block: 0;
 }
 
 :where(dd[class]) {
   margin-left: 0;
 }
 
 :where(fieldset[class]) {
   margin-left: 0;
   padding: 0;
   border: none;
 }
 
 /**
   Убираем стандартный маркер маркированному списку,
   у которого есть атрибут class
  */
 :where(ul[class]) {
   list-style: none;
 }
 
 /**
   Обнуляем вертикальные внешние отступы параграфа,
   объявляем локальную переменную для внешнего отступа вниз,
   чтобы избежать взаимодействие с более сложным селектором
  */
 p {
   --paragraphMarginBottom: 24px;
 
   margin-block: 0;
 }
 
 /**
   Внешний отступ вниз для параграфа без атрибута class,
   который расположен не последним среди своих соседних элементов
  */
 p:where(:not([class]):not(:last-child)) {
   margin-bottom: var(--paragraphMarginBottom);
 }
 
 
 /**
   Упрощаем работу с изображениями
  */
 img {
   display: block;
   max-width: 100%;
 }
 
 /**
   Наследуем свойства шрифт для полей ввода
  */
 input,
 textarea,
 select,
 button {
   font: inherit;
 }
 
 html {
   /**
     Пригодится в большинстве ситуаций
     (когда, например, нужно будет "прижать" футер к низу сайта)
    */
   height: 100%;
   /**
     Плавный скролл
    */
   scroll-behavior: smooth;
 }
 
 body {
   /**
     Пригодится в большинстве ситуаций
     (когда, например, нужно будет "прижать" футер к низу сайта)
    */
   min-height: 100%;
   /**
     Унифицированный интерлиньяж
    */
   line-height: 1.5;
 }
 
 /**
   Приводим к единому цвету svg-элементы
  */
 svg *[fill] { fill: currentColor }
 svg *[stroke] { stroke: currentColor }
 
 /**
   Чиним баг задержки смены цвета при взаимодействии с svg-элементами
  */
 svg * {
   transition-property: fill, stroke;
 }
 
 /**
   Удаляем все анимации и переходы для людей,
   которые предпочитают их не использовать
  */
 @media (prefers-reduced-motion: reduce) {
   * {
     animation-duration: 0.01ms !important;
     animation-iteration-count: 1 !important;
     transition-duration: 0.01ms !important;
     scroll-behavior: auto !important;
   }
 }

 :root {
    --background-color: #191919;
    --color-light: #FFFFFF;
    --color-accent: #118DA8;
    --color-dark: #000000;

    --font-family: 'DMSans', sans-serif;
    --font-size-title: clamp(32px, 4.44vw, 64px);
    --font-size-text: clamp(11px, 1.53vw, 22px);

    --border-radius-image: 10px;
    --border-radius-block: 25px;

    --container: 1440px;
    --container-padding-x: clamp(25px, 3.47vw, 50px);
    --container-padding-y: 40px;
    --container-padding-y-media: 25px;

    --transition-duration: .2s;
 }


 body {
    font-family: var(--font-family);
    font-size: var(--font-size-text);
    line-height: 1.1;
    font-weight: 400;

    color: var(--color-light);
    background-color: var(--background-color);
 }

 .visually-hidden {
    position: absolute !important;
    width: 1px !important;
    height: 1px !important;
    margin: -1px !important;
    border: 0 !important;
    padding: 0 !important;
    white-space: nowrap !important;
    clip-path: inset(100%) !important;
    clip: rect(0 0 0 0) !important;
    overflow: hidden !important;
}

 a, 
 button, 
 input, 
 textarea, 
 svg * {
    transition-duration: var(--transition-duration);
 }

 a {
    color: var(--color-light);
    text-decoration: none;
 }

 a:hover {
    color: var(--color-accent);
 }

 .container {
    max-width: var(--container);
    margin-inline: auto;
    padding-inline: var(--container-padding-x);
 }

 .accent-button {
    border: none;
    border-radius: var(--border-radius-image);
    padding: clamp(10px, 1.39vw, 20px);
    color: var(--color-light);
    background-color: var(--color-accent);
 }

 .accent-button:hover {
    filter: invert(1);
    transform: scale(1.05);
 }

 .input {
    padding: clamp(10px, 1.39vw, 20px);
    width: 100%;

    border: none;
    color: var(--color-light);
    background-color: var(--background-color);
    border-radius: var(--border-radius-image);
 }

 .input:hover,
 .input:focus {
    transform: scale(1.05);
 }

 .input:focus {
    color: var(--color-light);
 }

 




 /* Header */
 .header {
    /* position: sticky;
    top: 0;
    -webkit-box-shadow: 0px 5px 8px 0px rgba(88, 88, 88, 0.2);
    -moz-box-shadow: 0px 5px 8px 0px rgba(88, 88, 88, 0.2);
    box-shadow: 0px 5px 8px 0px rgba(88, 88, 88, 0.2);
    background-color: var(--background-color); */
 }

 .header-inner {
    /* width: calc(var(--container) - var(--container-padding-x) * 2);
    margin-inline: var(--container-padding-x);
    padding-inline: auto; */
    padding-block: var(--container-padding-y);
    display: flex;
    justify-content: space-between;
    align-items: center;
 }

 .header-logo-image {
    width: clamp(80px, 11.11vw, 160px);
    height: auto;
 }

 .header-logo-image:hover {
    transition-duration: var(--transition-duration);
    transform: scale(1.1);
 }

 .header-list {
    display: flex;
    justify-content: center;
    column-gap: clamp(20px, 2.78vw, 40px);
    font-size: clamp(8.5px, 1.18vw, 17px);
 }


 /* Intro */
 .intro-inner {
    padding-block: var(--container-padding-y);
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: clamp(30px, 4.17vw, 60px);
    align-items: center;
 }

 .intro-photo span {
    content: '';
    display: block;
    background: url('../images/icons/borders.svg') left top no-repeat;
    background-size: contain;
    -webkit-background-size: contain;
    /* width: clamp(34px, 5.14vw, 74px);
    height: auto; */
 }

 .intro-image {
    border-radius: var(--border-radius-image);
    width: clamp(325px, 45.14vw, 650px);
    height: auto;
 }

 .intro-text {
    display: flex;
    flex-flow: column;
 }

 .intro-title {
    display: block;
    width: clamp(265px, 36.81vw, 530px);
    height: auto;
    font-size: clamp(35px, 4.86vw, 70px);
 }

 .intro-title i {
    font-style: normal;
    background: url('../images/icons/border-bottom.svg') center bottom no-repeat;
    background-size: clamp(81.5px, 11.32vw, 163px) auto;
    -webkit-background-size: clamp(81.5px, 11.32vw, 163px) auto;
 }

 .intro-title b {
    font-size: clamp(40px, 5.56vw, 80px);
 }

 .intro-title:not(:last-child) {
    margin-bottom: 105px;
 }

 .intro-description p {
    font-size: clamp(7.5px, 1.04vw, 15px);
 }

 .intro-description p:not(:last-child) {
    margin-bottom: 20px;
 }

 .intro-service-list {
    display: flex;
    column-gap: 15px;
 }

 .intro-service-link:hover {
    filter: contrast(300%);
 }

 .intro-service-link-image {
    width: clamp(16px, 7.27vw, 32px);
    height: auto;
 }

 .intro-service-link-image:hover {
    transition-duration: var(--transition-duration);
    transform: scale(1.1);
 }


 /* Episode */
 .episode {
    display: grid;
    grid-template-columns: 1fr;
 }

 .episode-inner {
    display: flex;
    justify-content: space-between;
    column-gap: 50px;
    align-items: center;
 }

 .episode-title {
    font-size: var(--font-size-title);
 }

 .episode-list {
    padding-block: calc(var(--container-padding-y-media) * 2);  
 }

 .episode-item {
    display: grid;
    grid-template-columns: 30% 65%;
    gap: 50px;

    border-radius: var(--border-radius-block);
    background-color: var(--color-dark);
    padding: var(--container-padding-y);
 }

 .episode-item:not(:last-child) {
    margin-bottom: var(--container-padding-y);
 }

 .episode-item-image {
    border-radius: var(--border-radius-image);
    width: clamp(194.5px, 27.01vw, 389px);
    height: auto;
 }

 .episode-item-text {
    display: flex;
    flex-flow: column;
    justify-content: space-between;
    align-items: start;
 }

 .episode-item-hashtag {
    background-color: var(--background-color);
    border-radius: var(--border-radius-block);

    text-align: center;
    padding: 5px clamp(7.5px, 1.04vw, 15px);
 }

 .episode-item-subtitle {
    color: var(--color-accent);
    font-size: clamp(9px, 1.25vw, 18px);
 }
 

 /* Meet */
 .meet {
    padding-block: 100px;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 50px;
    align-items: center;
 }

 .meet-button {
    position: relative;
    width: clamp(56px, 7.78vw, 112px);
    aspect-ratio: 1;
    background-color: var(--color-accent);
    border: none;
    border-radius: 50%;
 }

 .meet-button:hover {
    filter: invert(1);
    transform: scale(1.05);
 }

 .meet-button-image {
    position: absolute;
    top: 50%;
    left: 50%;
    translate: -50% -50%;

    width: clamp(40px, 6.94vw, 100px);
    aspect-ratio: 1;
 }

 .meet-title {
    font-size: var(--font-size-title);
 }

 .meet-button:not(:last-child) {
    margin-bottom: 10px;
 }

 .meet-subtitle:not(:last-child)  {
    margin-bottom: 5px;
 }
 
 .meet-title:not(:last-child),
 .meet-description:not(:last-child) {
    margin-bottom: 20px;
 }

 .meet-image {
    border-radius: var(--border-radius-image);
    width: clamp(325px, 45.14vw, 650px);
    height: auto;
 }


/* Subscribe */
.subscribe {
    padding-block: 100px;
}

.subscribe-inner {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 50px;
}

.subscribe-subtitle:not(:last-child) {
    margin-bottom: 10px;
}

.subscribe-title {
    font-size: clamp(36px, 5vw, 72px);
}

.subscribe-input {
    margin-bottom: 20px;
}


/* Review */
.review {
    padding-block: 100px;
}

.review-list {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 15px;
}

.review-item {
    padding: clamp(25px, 3.47vw, 50px);
    background-color: var(--color-dark);
    border-radius: var(--border-radius-block);
}

.review-item-stars {
    background: url('../images/icons/star.svg') center repeat-x;

    width: 90px;
    height: 17px;
}

.review-item-comment {
    font-size: clamp(18px, 2.5vw, 36px);
}

.review-item-author {
    font-size: clamp(12px, 1.67vw, 24px);
}

.review-item-stars:not(:last-child),
.review-item-comment:not(:last-child) {
    margin-bottom: 25px;
}


/* Footer */
.footer {
    padding-block: 100px 50px;
}

.footer-inner {
    display: grid;
    grid-template-columns: 25% 70%;
    gap: 50px;
}

.footer-soc1als-list:not(:first-child) {
    margin-top: 30px;
}

.footer-soc1als-list {
    display: flex;
    column-gap: clamp(5px, 0.69vw, 10px);
}

.footer-soc1als-link-image {
    width: clamp(12px, 1.67vw, 24px);
    height: auto;
}

.footer-soc1als-link-image:hover {
    transition-duration: var(--transition-duration);
    transform: scale(1.1);
}

.footer-href {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    column-gap: 50px;
}

.footer-href-item:not(:last-child) {
    margin-bottom: 15px;
}



























 @media (max-width: 1024px) {

     /* Header */
    .header-inner {
        padding-block: var(--container-padding-y-media);
    }


    /* Intro */
    .intro-inner {
        padding-block: var(--container-padding-y-media);
    }


    /* Episode */
    .episode-list {
        padding-block: var(--container-padding-y-media);
    }

    .episode-item:not(:last-child) {
        margin-bottom: var(--container-padding-y-media);
    }


    /* Meet */
    .meet {
       padding-block: 50px;
    }


    /* Subscribe */
    .subscribe {
        padding-block: 50px;
    }


    /* Review */
    .review {
        padding-block: 50px;
    }


    /* Footer */
    .footer {
        padding-block: 50px 25px;
    }

    

 }



 @media (max-width: 767px) {

    /* Intro */
    .intro-title:not(:last-child) {
        margin-bottom: 50px;
    }


    /* Episode */
    .episode-item {
        gap: 25px;
    }

    .episode-item-description {
        font-size: 0;
    }


    /* Meet */
    .meet {
        gap: 25px;
    }

    .meet-button:not(:last-child) {
       margin-bottom: 5px;
    }

    .meet-subtitle:not(:last-child)  {
       margin-bottom: 0;
    }
    
    .meet-title:not(:last-child),
    .meet-description:not(:last-child) {
       margin-bottom: 10px;
    }

    
    /* Subscribe */
    .subscribe-inner {
        gap: 25px;
    }


    /* Footer */
    .footer-inner {
        grid-template-columns: 1fr;
    }

    .footer-soc1als-list:not(:first-child) {
        margin-top: 15px;
    }


 }




 @media (max-width: 640px) {

    /* Intro */
    .intro-inner {
        grid-template-columns: 1fr;
    }

    .intro-photo {
        margin-inline: auto;
    }

    .intro-text {
        align-items: center;
        column-gap: none;
    }


    /* Episode */
    .episode-item {
        grid-template-columns: 1fr;
    }

    .episode-item-image {
        margin-inline: auto;
    }

    .episode-item-hashtag:not(:last-child),
    .episode-item-subtitle:not(:last-child),
    .episode-item-description:not(:last-child) {
        margin-bottom: 15px;
    }


    /* Meet */
    .meet {
        grid-template-columns: 1fr;
    }

    .meet-inner {
        text-align: center;
    }

    .meet-description {
        text-align: left;
    }

    .meet-image {
        margin-inline: auto;
    }


    /* Subscribe */
    .subscribe-subtitle:not(:last-child) {
        margin-bottom: 5px;
    }
    
    .subscribe-input {
        margin-bottom: 10px;
    }


    /* Review */
    .review-list {
        grid-template-columns: repeat(2, 1fr);
        gap: 10px;
    }

    .review-item {
        text-align: center;
    }

    .review-item-stars {
        margin-inline: auto;
    }

    .review-item-stars:not(:last-child),
    .review-item-comment:not(:last-child) {
        margin-bottom: 15px;
    }


    /* Footer */
    .footer-href {
        grid-template-columns: repeat(2, 1fr);
    }
 }




 @media (max-width: 400px) {
    
    /* Intro */
    .intro-title:not(:last-child) {
       margin-bottom: 25px;
    }

    /* Meet */
    .meet {
        padding-block: 25px;
        gap: 15px;
    }


    /* Subscribe */
    .subscribe {
        padding-block: 25px;
    }

    .subscribe-inner {
        gap: 15px;
    }


    /* Review */
    .review {
        padding-block: 25px;
    }   


    /* Footer */
    .footer {
        padding-top: 25px;
    }
 }
    </style>
</head>
<body>

    <header class="header container">
        <div class="header-inner">
            <a href="#" class="header-logo">
                <img src="./assets/images/icons/logo.svg" 
                alt="Cataway Logo" 
                class="header-logo-image"
                width="160" height="33">
            </a>
    
            <nav class="header-nav">
                <ul class="header-list">
                    <li class="header-item">
                        <a href="#" class="header-link">Home</a>
                    </li>
    
                    <li class="header-item">
                        <a href="#" class="header-link">Episodes</a>
                    </li>
    
                    <li class="header-item">
                        <a href="#" class="header-link">About</a>
                    </li>
    
                    <li class="header-item">
                        <a href="#" class="header-link">Contact</a>
                    </li>
                </ul>
            </nav>
        </div>
    </header>

    <main class="content container">
        <h1 class="visually-hidden">Castaway Music</h1>

        <section class="intro">
            <div class="intro-inner">
                <div class="intro-photo">
                    <img src="./assets/images/intro.jpg" 
                    alt="Black Man Listen A Music" 
                    class="intro-image"
                    width="650" height="873">
                </div>
                

                <div class="intro-text">
                    <h2 class="intro-title">
                        Take your podcast to the <i>next</i> <b>level</b>
                    </h2>
    
                    <div class="intro-description">
                        <p>Listen on</p>
    
                        <div class="intro-service">
                            <ul class="intro-service-list">
                                <li class="intro-service-item">
                                    <a href="#" class="intro-service-link" target="_blank">
                                        <img src="./assets/images/music-service/1.svg" 
                                        alt="Spotify" 
                                        class="intro-service-link-image"
                                        width="32" height="32">
                                    </a>
                                </li>

                                <li class="intro-service-item">
                                    <a href="#" class="intro-service-link" target="_blank">
                                        <img src="./assets/images/music-service/2.svg" 
                                        alt="Spotify" 
                                        class="intro-service-link-image"
                                        width="32" height="32">
                                    </a>
                                </li>

                                <li class="intro-service-item">
                                    <a href="#" class="intro-service-link" target="_blank">
                                        <img src="./assets/images/music-service/3.svg" 
                                        alt="Spotify" 
                                        class="intro-service-link-image"
                                        width="32" height="32">
                                    </a>
                                </li>

                                <li class="intro-service-item">
                                    <a href="#" class="intro-service-link" target="_blank">
                                        <img src="./assets/images/music-service/4.svg" 
                                        alt="Spotify" 
                                        class="intro-service-link-image"
                                        width="32" height="32">
                                    </a>
                                </li>

                                <li class="intro-service-item">
                                    <a href="#" class="intro-service-link" target="_blank">
                                        <img src="./assets/images/music-service/5.svg" 
                                        alt="Spotify" 
                                        class="intro-service-link-image"
                                        width="32" height="32">
                                    </a>
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section class="episode">
            <div class="episode-inner">
                <h2 class="episode-title">
                    Latest episodes
                </h2>

                <button class="accent-button" type="button">
                    View all episodes
                </button>
            </div>

            <ul class="episode-list">
                <li class="episode-item">
                    <img src="./assets/images/episode/1.jpg" 
                    alt="Music Apparatura" 
                    class="episode-item-image"
                    width="389" height="465">

                    <div class="episode-item-text">
                        <div class="episode-item-hashtag">
                            <p>Gear</p>
                        </div>

                        <div class="episode-item-subtitle">
                            <p>Episode 3</p>
                        </div>

                        <h3 class="episode-title">
                            Should you get outboard audio gear?
                        </h3>

                        <div class="episode-item-description">
                            <p>Is hardware really worth it when it comes to podcasting? The answer is...it depends. Here’s our reasons on why you might want to consider picking something up.</p>
                        </div>

                        <button class="accent-button" type="button">
                            View Episode Details
                        </button>
                    </div>
                </li>

                <li class="episode-item">
                    <img src="./assets/images/episode/2.jpg" 
                    alt="Microphone" 
                    class="episode-item-image"
                    width="389" height="465">

                    <div class="episode-item-text">
                        <div class="episode-item-hashtag">
                            <p>Tips & Tricks</p>
                        </div>

                        <div class="episode-item-subtitle">
                            <p>Episode 2</p>
                        </div>

                        <h3 class="episode-title">
                            Mic tricks to take you to the next level
                        </h3>

                        <div class="episode-item-description">
                            <p>Stop rolling with those default settings on your mic. These small tweaks will take you from sounding good to great.</p>
                        </div>

                        <button class="accent-button" type="button">
                            View Episode Details
                        </button>
                    </div>
                </li>

                <li class="episode-item">
                    <img src="./assets/images/episode/3.jpg" 
                    alt="Black Ma Talking" 
                    class="episode-item-image"
                    width="389" height="465">

                    <div class="episode-item-text">
                        <div class="episode-item-hashtag">
                            <p>Gear</p>
                        </div>

                        <div class="episode-item-subtitle">
                            <p>Episode 1</p>
                        </div>

                        <h3 class="episode-title">
                            The best microphone under $200
                        </h3>

                        <div class="episode-item-description">
                            <p>With so many microphones on the market, how are you supposed to know what’s the best? Take a look at our top picks.</p>
                        </div>

                        <button class="accent-button" type="button">
                            View Episode Details
                        </button>
                    </div>
                </li>
            </ul>
        </section>

        <section class="meet">
            <div class="meet-inner">
                <button class="meet-button" type="button">
                    <img src="./assets/images/icons/right-arrow.svg" 
                    alt="Right Arrw" 
                    class="meet-button-image"
                    width="100" height="100">
                </button>

                <div class="meet-subtitle episode-item-subtitle">
                    <p>Meet your host</p>
                </div>

                <h3 class="meet-title">
                    Jacob Paulaner
                </h3>

                <div class="meet-description">
                    <p>
                        Jacob has a background in audio engineering, and has been podcasting since the early days.
                    </p>
                </div>

                <div class="meet-description">
                    <p>
                        He’s here to help you level up your game by sharing everything he’s learned along the way.
                    </p>
                </div>
            </div>

            <img src="./assets/images/jacob-pauler.jpg" 
            alt="Black Man Smiling" 
            class="meet-image"
            width="650" height="743">
        </section>

        <section class="subscribe">
            <div class="subscribe-inner episode-item">
                <div class="subscribe-text">
                    <div class="subscribe-subtitle episode-item-subtitle">
                        <p>Email Newsletter</p>
                    </div>

                    <h2 class="subscribe-title">
                        Subscribe for updates
                    </h2>
                </div>

                <form class="sumscribe-form">
                    <label for="username" class="visually-hidden">Name</label>
                    <input id="username" 
                    class="subscribe-input input" 
                    placeholder="Name">

                    <label for="useremail" class="visually-hidden">Email</label>
                    <input id="useremail" 
                    type="email"
                    class="subscribe-input input" 
                    placeholder="Email">

                    <button class="accent-button" type="submit">
                        Submit
                    </button>
                </form>
            </div>
        </section>

        <section class="review">
            <h2 class="visually-hidden">Reviews</h2>
            <ul class="review-list">
                <li class="review-item">
                    <div class="review-item-stars">
                        <span class="visually-hidden">5 stars</span>
                    </div>

                    <h3 class="review-item-comment">
                        I can’t recommend this podcast enough
                    </h3>

                    <h4 class="review-item-author">
                        Betty Lacey
                    </h4>
                </li>

                <li class="review-item">
                    <div class="review-item-stars">
                        <span class="visually-hidden">5 stars</span>
                    </div>

                    <h3 class="review-item-comment">
                        Jacob is the best in the business
                    </h3>

                    <h4 class="review-item-author">
                        Adam Driver
                    </h4>
                </li>

                <li class="review-item">
                    <div class="review-item-stars">
                        <span class="visually-hidden">5 stars</span>
                    </div>

                    <h3 class="review-item-comment">
                        A wealth of audio knowledge
                    </h3>

                    <h4 class="review-item-author">
                        Marcus Brown
                    </h4>
                </li>

                <li class="review-item">
                    <div class="review-item-stars">
                        <span class="visually-hidden">5 stars</span>
                    </div>

                    <h3 class="review-item-comment">
                        Every episode is a gem!
                    </h3>

                    <h4 class="review-item-author">
                        Jessica Knowl
                    </h4>
                </li>

                <li class="review-item">
                    <div class="review-item-stars">
                        <span class="visually-hidden">5 stars</span>
                    </div>

                    <h3 class="review-item-comment">
                        Whoa whoa, let me take some notes!
                    </h3>

                    <h4 class="review-item-author">
                        Scott Adams
                    </h4>
                </li>

                <li class="review-item">
                    <div class="review-item-stars">
                        <span class="visually-hidden">5 stars</span>
                    </div>

                    <h3 class="review-item-comment">
                        I’ve upped my game considerably since I started listening
                    </h3>

                    <h4 class="review-item-author">
                        Steven Blast
                    </h4>
                </li>
            </ul>
        </section>


    </main>

    <footer class="footer container">
        <div class="footer-inner">
            <div class="footer-logo">
                <a href="#" class="footer-logo-photo header-logo">
                    <img src="./assets/images/icons/logo.svg" 
                    alt="Cataway Logo" 
                    class="footer-logo-image header-logo-image"
                    width="160" height="33">
                </a>

                <ul class="footer-soc1als-list">
                    <li class="footer-soc1als-item">
                        <a href="#" class="footer-soc1als-link" target="_blank">
                            <img src="./assets/images/soc1als/instagram.svg" 
                            alt="Spotify" 
                            class="footer-soc1als-link-image"
                            width="24" height="24">
                        </a>
                    </li>

                    <li class="footer-soc1als-item">
                        <a href="#" class="footer-soc1als-link" target="_blank">
                            <img src="./assets/images/soc1als/twitter.svg" 
                            alt="Spotify" 
                            class="footer-soc1als-link-image"
                            width="24" height="24">
                        </a>
                    </li>

                    <li class="footer-soc1als-item">
                        <a href="#" class="footer-soc1als-link" target="_blank">
                            <img src="./assets/images/soc1als/facebook.svg" 
                            alt="Spotify" 
                            class="footer-soc1als-link-image"
                            width="24" height="24">
                        </a>
                    </li>
                </ul>
            </div>

            <div class="footer-href">
                <ul class="footer-href-list">
                    <li class="footer-href-item">
                        <a href="#" class="footer-href-link">Home</a>
                    </li>

                    <li class="footer-href-item">
                        <a href="#" class="footer-href-link">About</a>
                    </li>

                    <li class="footer-href-item">
                        <a href="#" class="footer-href-link">Episodes</a>
                    </li>

                    <li class="footer-href-item">
                        <a href="#" class="footer-href-link">Contact</a>
                    </li>
                </ul>

                <ul class="footer-href-list">
                    <li class="footer-href-item">
                        <a href="#" class="footer-href-link">Style Guide</a>
                    </li>

                    <li class="footer-href-item">
                        <a href="#" class="footer-href-link">Instructions</a>
                    </li>

                    <li class="footer-href-item">
                        <a href="#" class="footer-href-link">Changelog</a>
                    </li>

                    <li class="footer-href-item">
                        <a href="#" class="footer-href-link">Credit</a>
                    </li>

                    <li class="footer-href-item">
                        <a href="#" class="footer-href-link">Powered by Webflow</a>
                    </li>

                    <li class="footer-href-item">
                        <a href="#" class="footer-href-link">Licenses</a>
                    </li>
                </ul>

                <div class="intro-service">
                    <ul class="intro-service-list">
                        <li class="intro-service-item">
                            <a href="#" class="intro-service-link" target="_blank">
                                <img src="./assets/images/music-service/1.svg" 
                                alt="Spotify" 
                                class="intro-service-link-image"
                                width="32" height="32">
                            </a>
                        </li>

                        <li class="intro-service-item">
                            <a href="#" class="intro-service-link" target="_blank">
                                <img src="./assets/images/music-service/2.svg" 
                                alt="Spotify" 
                                class="intro-service-link-image"
                                width="32" height="32">
                            </a>
                        </li>

                        <li class="intro-service-item">
                            <a href="#" class="intro-service-link" target="_blank">
                                <img src="./assets/images/music-service/3.svg" 
                                alt="Spotify" 
                                class="intro-service-link-image"
                                width="32" height="32">
                            </a>
                        </li>

                        <li class="intro-service-item">
                            <a href="#" class="intro-service-link" target="_blank">
                                <img src="./assets/images/music-service/4.svg" 
                                alt="Spotify" 
                                class="intro-service-link-image"
                                width="32" height="32">
                            </a>
                        </li>

                        <li class="intro-service-item">
                            <a href="#" class="intro-service-link" target="_blank">
                                <img src="./assets/images/music-service/5.svg" 
                                alt="Spotify" 
                                class="intro-service-link-image"
                                width="32" height="32">
                            </a>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </footer>
    
    
</body>
</html>
