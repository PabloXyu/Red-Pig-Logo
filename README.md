# Red-Pig-Logo
SVG Code

```html
<?xml version="1.0" encoding="UTF-8"?>

<svg
    xmlns="http://www.w3.org/2000/svg"
    viewBox=" 0 0 100 100"
    style="background-color:transparent"
    width="400px" height="400px">

    <linearGradient id="RedPigColor">
        <stop stop-color="#DA1B5B"/><!-- Magenta -->
    </linearGradient>

    <linearGradient id="ItemColor">
        <stop stop-color="white"/><!-- White -->
    </linearGradient> 


    <!-- 0. Basic transform symbols, no explict display: -->
    <symbol id="RightHalf" style="fill:url(#RedPigColor)" >
        <path 
            d="M   0 100
               C  15 100
                  30  93
                  39  82
               S  50  60
                  50  50
                  42  29
                  34  18
               C  30  13
                  26   8
                  23   0
               C  20   4
                  16  12
                  16  13
               C   3  10
                  -3  10
                 -16  13
               Z  ">
        </path>
    </symbol>

    <symbol id="MinusOfPlus" >
        <path transform="translate(30,40)"
            stroke="url(#ItemColor)"
            stroke-width="6" 
            d="M -11 0 h 22" >
        </path>
   </symbol>


    <!-- 1. pig head shape -->
    <symbol id="Head" >
       <use href="#RightHalf" transform="translate(50,0)"/>
       <use href="#RightHalf" transform="scale(-1,1) translate(-50,0)"/>
    </symbol>
    

    <!-- 2. plus symbol (+) as the left eye symbol -->
    <symbol id="Plus" >
       <use href="#MinusOfPlus"/>
       <use href="#MinusOfPlus" transform="rotate(90,30,40)"/>
    </symbol>

    <!-- 3. minus symbol (-) as the right eye symbol" -->
    <symbol id="Minus" >
       <use href="#MinusOfPlus" transform="rotate(180,50,40)"/>
    </symbol>

    <!-- 4. ON/OFF symbol -->
    <symbol id="OnOffSymbol">

        <!-- 4A. the circle (o) of ON/OFF symbol -->
        <circle 
            style="fill:url(#RedPigColor)"
            stroke="url(#ItemColor)"
            stroke-width="5" 
            cx="50" cy="72" r="14" >
        </circle>

        <!-- 4B. circle-mask triangle -->
        <path style="fill:url(#RedPigColor)"
            d="M 50 72
               L 40 55
               H 60
               Z ">
        </path>

        <!-- 4C. vertical line (|) of ON/OFF symbol -->
        <path style="fill:url(#ItemColor)"
            d="M 48 56
               V 72
               H 52
               V 56
               Z ">
        </path>
    </symbol><!-- OnOff -->

    <!-- Animations -->

    <!-- 5A. plus symbol (+) rotated by click -->
    <symbol id="PlusClickRotated">
        <use href="#Plus" />
            <!-- 100°clockwise: 0.4s, 10°counterclockwise: 0.1s -->
            <animateTransform 
                attributeType="xml"
                attributeName="transform"
                type="rotate"
                values="0 30 40; 100 30 40;90 30 40"
                keyTimes="0; 0.8; 1"
                begin="click"
                dur="0.5s">
            </animateTransform>
    </symbol>

    <!-- 5B. plus symbol (+) rotated -->
    <symbol id="PlusRotated">
        <use href="#Plus" />
            <!-- deadlock: 19.4s; 100°clockwise: 0.4s, 10°counterclockwise: 0.1s -->
            <animateTransform 
                attributeType="xml"
                attributeName="transform"
                type="rotate"
                values="0 30 40;0 30 40; 100 30 40; 90 30 40"
                keyTimes="0; 0.975; 0.995; 1"
                repeatCount="indefinite"
                dur="20s">
            </animateTransform>
    </symbol>

    <!-- 6A. minus symbol (-) narrowed by click -->
    <symbol id="MinusClickNarrowed" >
        <path transform="translate(70,40)"
            stroke="url(#ItemColor)"
            stroke-width="6" 
            d="M -11 0 h 22" >
            <!-- close: 0.05s, open: 0.2s -->
            <animate
               attributeName="stroke-width" 
               values="6;0;6"
               keyTimes="0; 0.2; 1"
               begin="click"
               dur="0.25s">
           </animate>
        </path>
    </symbol>

    <!-- 6B. minus symbol (-) narrowed -->
    <symbol id="MinusNarrowed" >
        <path transform="translate(70,40)"
            stroke="url(#ItemColor)"
            stroke-width="6" 
            d="M -11 0 h 22" >
            <!-- deadlock: 24.75s; close: 0.05s, open: 0.2s -->
            <animate
               attributeName="stroke-width" 
               values="6;6;0;6"
               keyTimes="0; 0.990; 0.992; 1"
               repeatCount="indefinite"
               begin="10s"
               dur="25s">
           </animate>
        </path>
    </symbol>

    <!-- Red Pig Symbol-->

    <symbol id="RedPig">
        <use href="#Head" />
        <use href="#OnOffSymbol" />
        <!--use href="#Plus" /-->
        <!--use href="#PlusClickRotated" /-->
        <use href="#PlusRotated" />
        <!--use href="#Minus" /-->
        <!--use href="#MinusClickNarrowed" /-->
        <use href="#MinusNarrowed" />
    </symbol>

    <!-- Drawing 80%: -->
    <use href="#RedPig" transform=" scale(0.8) translate(10,10)" />
</svg>
```
