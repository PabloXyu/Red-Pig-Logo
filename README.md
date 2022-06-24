# Red-Pig-Logo
SVG Code
<!-- The same file as code is used in readme.md as an image -->
![red-pig-logo-svg](https://github.com/PabloXyu/Red-Pig-Logo/blob/main/Red%20Pig%20Animation.svg)
![red-pig-beziergon-svg](https://github.com/PabloXyu/Red-Pig-Logo/blob/main/Red%20Pig%20B%C3%A9ziergon%20Animation.svg)
## Red Pig Animation.svg
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
## Red Pig Béziergon Animation.svg
```
<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<svg
    xmlns="http://www.w3.org/2000/svg"
    viewBox=" 0 0 51 101"
    style="background-color:black"
    width="200px" height="400px">

    <linearGradient id="RedPigShape">
        <stop stop-color="#1BA7DA"/><!-- Blue -->
    </linearGradient> 

    <linearGradient id="CurveColor">
        <stop stop-color="#DA1B5B"/><!-- Magenta -->
    </linearGradient> 

    <linearGradient id="LineColor">
        <stop stop-color="#BADA1B"/><!-- Yellow -->
    </linearGradient> 

    <symbol id="RightHalf" >
        <path  stroke-width="0.1" style="stroke:url(#RedPigShape)"
            d="M   0 100
               C  15 100
                  30  93
                  39  82
               S  50  60
                  50  50
               S  42  29
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


    <!-- Bezier Curves-->

    <!-- C1 = Steps:16=15+1, Offset: 0, Duration:86=15+71 -->
    <symbol id="C1" >
        <path id="C1-curve" style="stroke:url(#CurveColor)" >
            <animate
                attributeName="d" 
                values="
                    M0 100  C0 100  0 100  0 100;
                    M0 100  C0 100 39  82 39  82;
                    M0 100  C0 100 39  82 39  82;
                    M15 100 C0 100 39  82 39  82;
                    M15 100 C0 100 39  82 39  82;
                    M15 100 C0 100 30  93 39  93;
                    M15 100 C0 100 30  93 39  93;
                    M15 100 C0 100 30  93 30  82;
                    M15 100 C0 100 30  93 30  82;
                    M15 100 C0 100 30  82 39  82;
                    M15 100 C0 100 30  82 39  82;
                    M0 100 C15 100 30  82 39  82;
                    M0 100 C15 100 30  82 39  82;
                    M0 100 C15 100 30  93 39  82;
                    M0 100 C15 100 30  93 39  82"
                repeatCount="indefinite"
                keyTimes="0;.012;.023;.035;.047;.058;.07;.081;.093;.105;.116;.128;.14;.151;1"
                dur="86s">
            </animate>
        </path><!-- C1-curve -->

        <g id="C1-lines" stroke="url(#LineColor)" stroke-width=".5">
            <animate id="C1-lines-fade-out"
                attributeName="opacity" 
                values="1;1;0;0"
                repeatCount="indefinite"
                keyTimes="0;.163;.174;1"
                dur="86s">
            </animate><!-- C1-lines-fade-out -->
            <path id="C1-line-begin">
                <animate
                    attributeName="d" 
                    values="
                        M0 100 l  0 0;
                        M0 100 l  0 0;
                        M0 100 l 15 0;
                        M0 100 l 15 0"
                    repeatCount="indefinite"
                    keyTimes="0;.023;.035;1"
                    dur="86s">
                </animate>
            </path><!-- C1-line-begin -->
            <path id="C1-line-end">
                <animate
                    attributeName="d" 
                    values="
                        M 39 82 l  0  0;
                        M 39 82 l  0  0;
                        M 39 82 l  0 11;
                        M 39 82 l  0 11;
                        M 39 82 l -9  0;
                        M 39 82 l -9  0;
                        M 39 82 l -9 11;
                        M 39 82 l -9 11"
                    repeatCount="indefinite"
                    begin="0s"                
                    keyTimes="0;.047;.058;.07;.081;.14;.151;1"
                    dur="86.0s">
                </animate>
            </path><!-- C1-line-end -->
        </g><!-- C1-lines -->
    </symbol><!-- C1 ==================================== -->

    <!-- C2 = Steps:16=15+1, Offset:16, Duration:70=15+55 -->
    <symbol id="C2" >
        <path id="C2-curve" style="stroke:url(#CurveColor)" >
            <animate
                attributeName="d" 
                values="
                    M39 82 C39 82 39 82 39 82;
                    M39 82 C39 82 50 50 50 50;
                    M39 82 C39 82 50 50 50 50;
                    M48 82 C39 82 50 50 50 50;
                    M48 82 C39 82 50 50 50 50;
                    M48 82 C39 82 50 50 50 60;
                    M48 82 C39 82 50 50 50 60;
                    M39 71 C39 71 50 50 50 60;
                    M39 71 C39 71 50 50 50 60;
                    M48 71 C39 71 50 50 50 60;
                    M48 71 C39 71 50 50 50 60;
                    M48 71 C39 71 50 60 50 50;
                    M48 71 C39 71 50 60 50 50;
                    M39 82 C48 71 50 60 50 50;
                    M39 82 C48 71 50 60 50 50;
                    M39 82 C48 71 50 60 50 50;
                    M39 82 C48 71 50 60 50 50"
                repeatCount="indefinite"
                keyTimes="0;.014;.029;.043;.057;.071;.086;.1;.114;.129;.143;.157;.171;.186;.2;.214;1"
                begin="16s"
                dur="70s">
            </animate>
        </path><!-- C2-curve -->

        <g id="C2-lines" stroke="url(#LineColor)" stroke-width=".5">
            <animate id="C2-lines-fade-out"
                attributeName="opacity" 
                values="1;1;0;0"
                repeatCount="indefinite"
                keyTimes="0;.2;.214;1"
                begin="16s"
                dur="70s">
            </animate><!-- C2-lines-fade-out -->
            <path id="C2-line-begin">
                <animate
                    attributeName="d" 
                    values="
                        M39 82 l  0 0;
                        M39 82 l  0 0;
                        M39 82 l9   0;
                        M39 82 l9   0;
                        M39 82 l0 -11;
                        M39 82 l0 -11;
                        M39 82 l9 -11;
                        M39 82 l9 -11"
                    repeatCount="indefinite"
                keyTimes="0;.029;.043;.086;.1;.114;.129;1"
                begin="16s"
                dur="70s">
                </animate>
            </path><!-- C2-line-begin -->
            <path id="C2-line-end">
                <animate
                    attributeName="d" 
                    values="
                        M 50 50 l  0   0;
                        M 50 50 l  0   0;
                        M 50 50 l  0  10;
                        M 50 50 l  0  10"
                    repeatCount="indefinite"
                    keyTimes="0;.057;.071;1"
                    begin="16s"
                    dur="70s">
                </animate>
            </path><!-- C2-line-end -->
        </g><!-- C2-lines -->
    </symbol><!-- C2 ==================================== -->

    <!-- C3 = Steps:16=15+1, Offset:32, Duration:54=15+39 -->
    <symbol id="C3" >
        <path id="C3-curve" style="stroke:url(#CurveColor)" >
            <animate
                attributeName="d" 
                values="
                    M50 50 C50 50 50 50 50 50;
                    M50 50 C50 50 34 18 34 18;
                    M50 50 C50 50 34 18 34 18;
                    M50 40 C50 50 34 18 34 18;
                    M50 40 C50 50 34 18 34 18;
                    M50 40 C50 50 34 18 42 18;
                    M50 40 C50 50 34 18 42 18;
                    M50 40 C50 50 34 18 34 29;
                    M50 40 C50 50 34 18 34 29;
                    M50 40 C50 50 34 29 34 18;
                    M50 40 C50 50 34 29 34 18;
                    M50 50 C50 40 34 29 34 18;
                    M50 50 C50 40 34 29 34 18;
                    M50 50 C50 40 42 29 34 18;
                    M50 50 C50 40 42 29 34 18;
                    M50 50 C50 40 42 29 34 18;
                    M50 50 C50 40 42 29 34 18"
                repeatCount="indefinite"
                keyTimes="0;.019;.037;.056;.074;.093;.111;.13;.148;.167;.185;.204;.222;.241;.259;.278;1"
                begin="32s"
                dur="54s">
            </animate>
        </path><!-- C3-curve -->

        <g id="C3-lines" stroke="url(#LineColor)" stroke-width=".5">
            <animate id="C3-lines-fade-out"
                attributeName="opacity" 
                values="1;1;0;0"
                repeatCount="indefinite"
                keyTimes="0;.259;.278;1"
                begin="32s"
                dur="54s">
            </animate><!-- C3-lines-fade-out -->
            <path id="C3-line-begin">
                <animate
                    attributeName="d" 
                    values="
                        M 50 50 l  0   0;
                        M 50 50 l  0   0;
                        M 50 50 l  0 -10;
                        M 50 50 l  0 -10"
                    repeatCount="indefinite"
                    keyTimes="0;.037;.056;1"
                    begin="32s"
                    dur="54s">
                </animate>
            </path><!-- C3-line-begin -->
            <path id="C3-line-end">
                <animate
                    attributeName="d" 
                    values="
                        M 34 18 l  0  0;
                        M 34 18 l  0  0;
                        M 34 18 l  8  0;
                        M 34 18 l  8  0;
                        M 34 18 l  0 11;
                        M 34 18 l  0 11;
                        M 34 18 l  8 11;
                        M 34 18 l  8 11"
                    repeatCount="indefinite"
                    keyTimes="0;.074;.093;.111;.13;.222;.241;1"
                    begin="32s"
                    dur="54s">
                </animate>
            </path><!-- C3-line-end -->
        </g><!-- C3-lines -->
    </symbol><!-- C3 ==================================== -->

    <!-- C4 = Steps:20=19+1, Offset:48, Duration:38=19+19 -->
    <symbol id="C4" >
        <path id="C4-curve" style="stroke:url(#CurveColor)" >
            <animate
                attributeName="d" 
                values="
                    M34 18 C34 18 34 18 34 18;
                    M34 18 C34 18 23  0 23  0;
                    M34 18 C34 18 23  0 23  0;
                    M30 18 C34 18 23  0 23  0;
                    M30 18 C34 18 23  0 23  0;
                    M30 18 C34 18 23  0 26  0;
                    M30 18 C34 18 23  0 26  0;
                    M34 13 C34 18 23  0 26  0;
                    M34 13 C34 18 23  0 26  0;
                    M34 13 C34 18 23  0 23  8;
                    M34 13 C34 18 23  0 23  8;
                    M34 13 C34 18 23  8 23  0;
                    M34 13 C34 18 23  8 23  0;
                    M34 18 C34 13 23  8 23  0;
                    M34 18 C34 13 23  8 23  0;
                    M34 18 C34 13 26  8 23  0;
                    M34 18 C34 13 26  8 23  0;
                    M34 18 C30 13 26  8 23  0;
                    M34 18 C30 13 26  8 23  0;
                    M34 18 C30 13 26  8 23  0;
                    M34 18 C30 13 26  8 23  0"
                repeatCount="indefinite"
                keyTimes="0;.026;.053;.079;.105;.132;.158;.184;.211;.237;.263;.289;.316;.342;.368;.395;.421;.447;.474;.5;1"
                begin="48s"
                dur="38s">
            </animate>
        </path><!-- C4-curve -->

        <g id="C4-lines" stroke="url(#LineColor)" stroke-width=".5">
            <animate id="C4-lines-fade-out"
                attributeName="opacity" 
                values="1;1;0;0"
                repeatCount="indefinite"
                keyTimes="0;.474;.5;1"
                begin="48s"
                dur="38s">
            </animate><!-- C4-lines-fade-out -->
            <path id="C4-line-begin">
                <animate
                    attributeName="d" 
                    values="
                        M 34 18 l  0 0;
                        M 34 18 l  0 0;
                        M 34 18 l -4 0;
                        M 34 18 l -4 0;
                        M 34 18 l  0 -5;
                        M 34 18 l  0 -5;
                        M 34 18 l -4 -5;
                        M 34 18 l -4 -5"
                    repeatCount="indefinite"
                    keyTimes="0;.053;.079;.158;.184;.421;.447;1"
                    begin="48s"
                    dur="38s">
                </animate>
            </path><!-- C4-line-begin -->
            <path id="C4-line-end">
                <animate
                    attributeName="d" 
                    values="
                        M23 0 l0 0;
                        M23 0 l0 0;
                        M23 0 l3 0;
                        M23 0 l3 0;
                        M23 0 l0 8;
                        M23 0 l0 8;
                        M23 0 l3 8;
                        M23 0 l3 8"
                    repeatCount="indefinite"
                keyTimes="0;.105;.132;.211;.237;.368;.395;1"
                begin="48s"
                dur="38s">
                </animate>
            </path><!-- C4-line-end -->
        </g><!-- C4-lines -->
    </symbol><!-- C4 ==================================== -->

    <!-- C5 = Steps: 8= 7+1, Offset:68, Duration:18= 7+11 -->
    <symbol id="C5" >
        <path id="C5-curve" style="stroke:url(#CurveColor)" >
            <animate
                attributeName="d" 
                values="
                    M23  0 C23  0 23  0 23  0;
                    M23  0 C23  0 16 13 16 13;
                    M23  0 C23  0 16 13 16 13;
                    M23  0 C23  4 16 13 16 12;
                    M23  0 C23  4 16 13 16 12;
                    M23  0 C20  4 16 13 16 12;
                    M23  0 C20  4 16 13 16 12;
                    M23  0 C20  4 16 13 16 12;
                    M23  0 C20  4 16 13 16 12"
                repeatCount="indefinite"
                keyTimes="0;.056;.111;.167;.222;.278;.333;.389;1"
                begin="68s"
                dur="18s">
            </animate>
        </path><!-- C5-curve -->

        <g id="C5-lines" stroke="url(#LineColor)" stroke-width=".5">
            <animate id="C5-lines-fade-out"
                attributeName="opacity" 
                values="1;1;0;0"
                repeatCount="indefinite"
                keyTimes="0;.333;.389;1"
                begin="68s"
                dur="18s">
            </animate><!-- C5-lines-fade-out -->
            <path id="C5-line-begin">
                <animate
                    attributeName="d" 
                    values="
                        M 23  0 l  0 0;
                        M 23  0 l  0 0;
                        M 23  0 l  0 4;
                        M 23  0 l  0 4;
                        M 23  0 l -3 4;
                        M 23  0 l -3 4"
                    repeatCount="indefinite"
                    keyTimes="0;.111;.167;.222;.278;1"
                    begin="68s"
                    dur="18s">
                </animate>
            </path><!-- C5-line-begin -->
            <path id="C5-line-end">
                <animate
                    attributeName="d" 
                    values="
                        M16 13 l  0  0;
                        M16 13 l  0  0;
                        M16 13 l  0 -1;
                        M16 13 l  0 -1;"
                    repeatCount="indefinite"
                    keyTimes="0;.111;.167;1"
                    begin="68s"
                    dur="18s">
                </animate>
            </path><!-- C5-line-end -->
        </g><!-- C5-lines -->
    </symbol><!-- C5 ==================================== -->

    <!-- C6 = Steps: 8= 7+1, Offset:76, Duration:10= 7+3  -->
    <symbol id="C6" >
        <path id="C6-curve" style="stroke:url(#CurveColor)" >
            <animate
                attributeName="d" 
                values="
                    M16 13 C16 13 16 13  16 13;
                    M16 13 C 3 13  0 13   0 13;
                    M16 13 C 3 13  0 13   0 13;
                    M16 13 C 3 13 -3 13 -16 13;
                    M16 13 C 3 13 -3 13 -16 13;
                    M16 13 C 3 10 -3 10 -16 13;
                    M16 13 C 3 10 -3 10 -16 13;
                    M16 13 C 3 10 -3 10 -16 13;
                    M16 13 C 3 10 -3 10 -16 13"
                repeatCount="indefinite"
                keyTimes="0;.1;.2;.3;.4;.5;.6;.7;1"
                begin="76s"
                dur="10s">
            </animate>
        </path><!-- C6-curve -->

        <g id="C6-lines" stroke="url(#LineColor)" stroke-width=".5">
            <animate id="C6-lines-fade-out"
                attributeName="opacity" 
                values="1;1;0;0"
                repeatCount="indefinite"
                keyTimes="0;.6;.7;1"
                begin="76s"
                dur="10s">
            </animate><!-- C6-lines-fade-out -->
            <path id="C6-line-begin">
                <animate
                    attributeName="d" 
                    values="
                        M 16 13 l  0 0;
                        M 16 13 l  0 0;
                        M 16 13 L 3 13;
                        M 16 13 L 3 13;
                        M 16 13 L 3 10;
                        M 16 13 L 3 10"
                    repeatCount="indefinite"
                    keyTimes="0;.2;.3;.4;.5;1"
                    begin="76s"
                    dur="10s">
                </animate>
            </path><!-- C6-line-begin -->
        </g><!-- C6-lines -->
    </symbol><!-- C6 ==================================== -->

    <symbol id="Image">
        <use href="#RightHalf"/>
        <use href="#C1"/>
        <use href="#C2"/>
        <use href="#C3"/>
        <use href="#C4"/>
        <use href="#C5"/>
        <use href="#C6"/>
    </symbol>
    
    <!-- Drawing 80%: -->
    <!--use href="#Image" transform=" scale(0.8) translate(10,10)" /-->

    <!-- Drawing 100%: -->
    <use href="#Image"  />

</svg>
```html
