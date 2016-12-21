---
title: "is, isw 루틴 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
f1_keywords: 
  - "isw"
  - "is"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "is 루틴"
  - "isw 루틴"
ms.assetid: 1e171a57-2cde-41f6-a75f-a080fa3c12e5
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is, isw 루틴
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

|||  
|-|-|  
|[isalnum, iswalnum, \_isalnum\_l, \_iswalnum\_l](../c-runtime-library/reference/isalnum-iswalnum-isalnum-l-iswalnum-l.md)|[isgraph, iswgraph, \_isgraph\_l, \_iswgraph\_l](../c-runtime-library/reference/isgraph-iswgraph-isgraph-l-iswgraph-l.md)|  
|[isalpha, iswalpha, \_isalpha\_l, \_iswalpha\_l](../c-runtime-library/reference/isalpha-iswalpha-isalpha-l-iswalpha-l.md)|[isleadbyte, \_isleadbyte\_l](../c-runtime-library/reference/isleadbyte-isleadbyte-l.md)|  
|[isascii, \_\_isascii, iswascii](../c-runtime-library/reference/isascii-isascii-iswascii.md)|[islower, iswlower, \_islower\_l, \_iswlower\_l](../c-runtime-library/reference/islower-iswlower-islower-l-iswlower-l.md)|  
|[isblank, iswblank, \_isblank\_l, \_iswblank\_l](../c-runtime-library/reference/isblank-iswblank-isblank-l-iswblank-l.md)|[isprint, iswprint, \_isprint\_l, \_iswprint\_l](../c-runtime-library/reference/isprint-iswprint-isprint-l-iswprint-l.md)|  
|[iscntrl, iswcntrl, \_iscntrl\_l, \_iswcntrl\_l](../c-runtime-library/reference/iscntrl-iswcntrl-iscntrl-l-iswcntrl-l.md)|[ispunct, iswpunct, \_ispunct\_l, \_iswpunct\_l](../c-runtime-library/reference/ispunct-iswpunct-ispunct-l-iswpunct-l.md)|  
|[iscsym, iscsymf, \_\_iscsym, \_\_iswcsym, \_\_iscsymf, \_\_iswcsymf, \_iscsym\_l, \_iswcsym\_l, \_iscsymf\_l, \_iswcsymf\_l](../c-runtime-library/reference/iscsym-functions.md)|[isspace, iswspace, \_isspace\_l, \_iswspace\_l](../c-runtime-library/reference/isspace-iswspace-isspace-l-iswspace-l.md)|  
|[\_isctype, iswctype, \_isctype\_l, \_iswctype\_l](../c-runtime-library/reference/isctype-iswctype-isctype-l-iswctype-l.md)|[isupper, \_isupper\_l, iswupper, \_iswupper\_l](../c-runtime-library/reference/isupper-isupper-l-iswupper-iswupper-l.md)|  
|[isdigit, iswdigit, \_isdigit\_l, \_iswdigit\_l](../c-runtime-library/reference/isdigit-iswdigit-isdigit-l-iswdigit-l.md)|[isxdigit, iswxdigit, \_isxdigit\_l, \_iswxdigit\_l](../c-runtime-library/reference/isxdigit-iswxdigit-isxdigit-l-iswxdigit-l.md)|  
  
## 설명  
 이러한 루틴은 지정된 조건에 대해 문자를 테스트합니다.  
  
 **is** 는 \-1\(`EOF`\) 부터 **UCHAR\_MAX** \(0xFF\) 까지 모두 포함하여 정수 인자에 대해 의미있는 결과를 생산합니다.  정상적인 인수 형식은 `int` 입니다.  
  
> [!CAUTION]
>  **is** 루틴의 경우 `char` 형식의 인자를 전달 할 경우 예기치 못한 결과가 발생할 수 있습니다.  0x7F 보다 큰 값의 `char` 형식의 SBCS나 MBCS 싱글 바이트 문자는 음수입니다.  만약 `char` 가 전달되면 컴파일러가 값을 signed `int` 또는 signed **long** 으로 변환할 수 있습니다.  이 값은 예기치 못한 결과로 컴파일러에 의해 부호 확장 될 수있습니다.  
  
 **isw** 루틴은 \-1\(**WEOF**\) 부터 0xFFFF 까지 모두 포함하여 어떤 정수 값에 대해서도 의미있는 결과를 생성합니다.   **wint\_t** 데이터 타입은 **unsigned short** 으로 WCHAR.H 내에 지정 되어 있으며, 와이드 문자나 wide\-character end\-of\-file\(**WEOF**\) 값을 보유 할 수있습니다.  
  
 출력 값은 로캘의 `LC_CTYPE` 범주 설정에 영향을 받습니다. 자세한 내용은 [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)을 참조하십시오.  이 **\_l** 접미사가 없는 이러한 함수의 버전은 해당 로캘 종속 동작에 현재 로캘을 사용합니다. **\_l** 접미사가 있는 버전은 대신 전달 된 로캘 매개 변수를 사용하는 경우을 제외하고는 동일합니다.  
  
 "C" 로캘에서 **is** 루틴에 대한 테스트 조건은 다음과 같습니다.  
  
 `isalnum`  
 영숫자 \(A – Z, a – z, or 0 – 9\).  
  
 `isalpha`  
 알파벳 \(A – Z or a – z\).  
  
 `__isascii`  
 ASCII 문자 \(0x00 – 0x7F\).  
  
 `isblank`  
 가로 탭 또는 공백 문자 \(0x09 or 0x20\).  
  
 `iscntrl`  
 Control character \(0x00 – 0x1F or 0x7F\).  
  
 `__iscsym`  
 Letter, underscore, or digit.  
  
 `__iscsymf`  
 Letter or underscore.  
  
 **isdigit**  
 10진수 \(0 – 9\).  
  
 `isgraph`  
 Printable character except space \( \).  
  
 `islower`  
 소문자 \(a – z\).  
  
 `isprint`  
 Printable character including space \(0x20 – 0x7E\).  
  
 `ispunct`  
 Punctuation character.  
  
 `isspace`  
 공백 문자 \(0x09 – 0x0D or 0x20\).  
  
 `isupper`  
 대문자 \(A – Z\).  
  
 `isxdigit`  
 16진수 \(A – F, a – f, or 0 – 9\).  
  
 **isw** 루틴에 대해 지정된 조건에서의 테스트 결과는 로캘과 무관합니다.   **isw** 함수에 대한 테스트 조건은 다음과 같습니다.  
  
 `iswalnum`  
 `iswalpha` 또는 `iswdigit`  
  
 `iswalpha`  
 `iswcntrl`, `iswdigit`, `iswpunct`, 또는 `iswspace` 에 대한 것이 아닌 구현이 정의 된 설정 중의 하나인 어떠한 와이드문자도 0이 아닙니다.  `iswalpha` 는 `iswupper` 또는 `iswlower` 가 0이 아닌 와이드 문자에 대해서만 0이 아닌 값을 반환합니다.  
  
 `iswascii`  
 Wide\-character representation of ASCII character \(0x0000 – 0x007F\).  
  
 `iswblank`  
 표준 공백 문자에 해당하거나 `iswalnum` 에 대한 와이드 문자의 구현이 정의된 설정 중 하나인 와이드 문자는 false입니다.  표준 공백 문자는 공백 \(L' '\) 및 가로 탭 \('\\t' L\) 입니다.  
  
 `iswcntrl`  
 와이드 문자를 제어 합니다.  
  
 **\_\_iswcsym**  
 Any wide character for which **isalnum** is true, or the '\_' character.  
  
 **\_\_iswcsymf**  
 Any wide character for which `iswalpha` is true, or the '\_' character.  
  
 `iswctype`  
 문자는 `desc` 인수에 의해 지정된 속성을 가지고 있습니다.  아래의 테이블이 보여주는 것처럼 `iswctype` 의 `desc` 인수의 유효한 각 값에 대해 동등한 유형의 루틴이 존재합니다.  
  
 **Equivalence of iswctype\(**   
 ***c, desc* \) to Other isw Testing Routines**  
  
|*desc* 인수 값|iswctype\( *c, desc* \) equivalent|  
|-----------------|----------------------------------------|  
|**\_ALPHA**|**iswalpha\(** `c` **\)**|  
|**\_ALPHA** &#124; **\_DIGIT**|**iswalnum\(** `c` **\)**|  
|**\_BLANK**|**iswblank\(** `c` **\)**|  
|**\_CONTROL**|**iswcntrl\(** `c` **\)**|  
|**\_DIGIT**|**iswdigit\(** `c` **\)**|  
|**\_ALPHA** &#124; **\_DIGIT** &#124; **\_PUNCT**|**iswgraph\(** `c` **\)**|  
|**\_LOWER**|**iswlower\(** `c` **\)**|  
|**\_ALPHA** &#124; **\_BLANK** &#124; **\_DIGIT** &#124; **\_PUNCT**|**iswprint\(** `c` **\)**|  
|**\_PUNCT**|**iswpunct\(** `c` **\)**|  
|**\_BLANK**|**iswblank\(** `c` **\)**|  
|**\_SPACE**|**iswspace\(** `c` **\)**|  
|**\_UPPER**|**iswupper\(** `c` **\)**|  
|**\_HEX**|**iswxdigit\(** `c` **\)**|  
  
 `iswdigit`  
 10진수 문자에 해당하는 와이드 문자입니다.  
  
 `iswgraph`  
 공백 와이드 문자를 제외하고 인쇄할 수 있는 와이드 문자 \(L' '\).  
  
 `iswlower`  
 소문자 또는 `iswcntrl`, `iswdigit`, `iswpunct`, 또는 `iswspace` 에 대한 것이 아닌 와이드 문자의 구현이 정의된 설정 중의 하나는 0이 아닙니다.  `iswlower` 는 소문자에 해당하는 와이드 문자에 대해서만 0이 아닌 값을 반환합니다.  
  
 `iswprint`  
 공백 와이드 문자를 포함하고 인쇄할 수 있는 와이드 문자 \(L' '\).  
  
 `iswpunct`  
 공백 와이드 문자 \(L' '\) 도 아니고 와이드 문자에 대해 `iswalnum` 가 0이 아닌 인쇄 할 수 있는 와이드 문자  
  
 `iswspace`  
 표준 공백 문자에 대응하거나 `iswalnum` 에 대한 와이드 문자의 구현이 정의된 설정 중 하나인 와이드 문자는 false입니다.  표준 공백 문자 : 공백\(L' '\), 폼 피드\(L '\\f'\), 줄 바꿈 \('\\n' L\), 캐리지 리턴 \('\\r' L\), 가로 탭\(L '\\t'\), 세로 탭 \(L '\\v'\).  
  
 `iswupper`  
 대문자 이거나 `iswcntrl`, `iswdigit`, `iswpunct`, 또는 `iswspace` 에 대한 것이 아닌 와이드 문자의 구현이 정의된 설정 중에 하나인 와이드 문자는 0이 아닙니다.  `iswupper` 는 대문자에 해당하는 와이드 문자에 대해서만 0이 아닌 값을 반환합니다.  
  
 `iswxdigit`  
 16진수 문자에 해당하는 와이드 문자  
  
## 예제  
  
```  
// crt_isfam.c  
/* This program tests all characters between 0x0  
 * and 0x7F, then displays each character with abbreviations  
 * for the character-type codes that apply.  
 */  
  
#include <stdio.h>  
#include <ctype.h>  
  
int main( void )  
{  
   int ch;  
   for( ch = 0; ch <= 0x7F; ch++ )  
   {  
      printf( "%.2x  ", ch );  
      printf( " %c", isprint( ch )  ? ch   : ' ' );  
      printf( "%4s", isalnum( ch )  ? "AN" : "" );  
      printf( "%3s", isalpha( ch )  ? "A"  : "" );  
      printf( "%3s", __isascii( ch )  ? "AS" : "" );  
      printf( "%3s", iscntrl( ch )  ? "C"  : "" );  
      printf( "%3s", __iscsym( ch )  ? "CS "  : "" );  
      printf( "%3s", __iscsymf( ch )  ? "CSF"  : "" );  
      printf( "%3s", isdigit( ch )  ? "D"  : "" );  
      printf( "%3s", isgraph( ch )  ? "G"  : "" );  
      printf( "%3s", islower( ch )  ? "L"  : "" );  
      printf( "%3s", ispunct( ch )  ? "PU" : "" );  
      printf( "%3s", isspace( ch )  ? "S"  : "" );  
      printf( "%3s", isprint( ch )  ? "PR" : "" );  
      printf( "%3s", isupper( ch )  ? "U"  : "" );  
      printf( "%3s", isxdigit( ch ) ? "X"  : "" );  
      printf( ".\n" );  
   }  
}  
```  
  
## Output  
  
```  
00            AS  C                              .  
01            AS  C                              .  
02            AS  C                              .  
03            AS  C                              .  
04            AS  C                              .  
05            AS  C                              .  
06            AS  C                              .  
07            AS  C                              .  
08            AS  C                              .  
09            AS  C                    S         .  
0a            AS  C                    S         .  
0b            AS  C                    S         .  
0c            AS  C                    S         .  
0d            AS  C                    S         .  
0e            AS  C                              .  
0f            AS  C                              .  
10            AS  C                              .  
11            AS  C                              .  
12            AS  C                              .  
13            AS  C                              .  
14            AS  C                              .  
15            AS  C                              .  
16            AS  C                              .  
17            AS  C                              .  
18            AS  C                              .  
19            AS  C                              .  
1a            AS  C                              .  
1b            AS  C                              .  
1c            AS  C                              .  
1d            AS  C                              .  
1e            AS  C                              .  
1f            AS  C                              .  
20            AS                       S PR      .  
21   !        AS              G    PU    PR      .  
22   "        AS              G    PU    PR      .  
23   #        AS              G    PU    PR      .  
24   $        AS              G    PU    PR      .  
25   %        AS              G    PU    PR      .  
26   &        AS              G    PU    PR      .  
27   '        AS              G    PU    PR      .  
28   (        AS              G    PU    PR      .  
29   )        AS              G    PU    PR      .  
2a   *        AS              G    PU    PR      .  
2b   +        AS              G    PU    PR      .  
2c   ,        AS              G    PU    PR      .  
2d   -        AS              G    PU    PR      .  
2e   .        AS              G    PU    PR      .  
2f   /        AS              G    PU    PR      .  
30   0  AN    AS   CS      D  G          PR     X.  
31   1  AN    AS   CS      D  G          PR     X.  
32   2  AN    AS   CS      D  G          PR     X.  
33   3  AN    AS   CS      D  G          PR     X.  
34   4  AN    AS   CS      D  G          PR     X.  
35   5  AN    AS   CS      D  G          PR     X.  
36   6  AN    AS   CS      D  G          PR     X.  
37   7  AN    AS   CS      D  G          PR     X.  
38   8  AN    AS   CS      D  G          PR     X.  
39   9  AN    AS   CS      D  G          PR     X.  
3a   :        AS              G    PU    PR      .  
3b   ;        AS              G    PU    PR      .  
3c   <        AS              G    PU    PR      .  
3d   =        AS              G    PU    PR      .  
3e   >        AS              G    PU    PR      .  
3f   ?        AS              G    PU    PR      .  
40   @        AS              G    PU    PR      .  
41   A  AN  A AS   CS CSF     G          PR  U  X.  
42   B  AN  A AS   CS CSF     G          PR  U  X.  
43   C  AN  A AS   CS CSF     G          PR  U  X.  
44   D  AN  A AS   CS CSF     G          PR  U  X.  
45   E  AN  A AS   CS CSF     G          PR  U  X.  
46   F  AN  A AS   CS CSF     G          PR  U  X.  
47   G  AN  A AS   CS CSF     G          PR  U   .  
48   H  AN  A AS   CS CSF     G          PR  U   .  
49   I  AN  A AS   CS CSF     G          PR  U   .  
4a   J  AN  A AS   CS CSF     G          PR  U   .  
4b   K  AN  A AS   CS CSF     G          PR  U   .  
4c   L  AN  A AS   CS CSF     G          PR  U   .  
4d   M  AN  A AS   CS CSF     G          PR  U   .  
4e   N  AN  A AS   CS CSF     G          PR  U   .  
4f   O  AN  A AS   CS CSF     G          PR  U   .  
50   P  AN  A AS   CS CSF     G          PR  U   .  
51   Q  AN  A AS   CS CSF     G          PR  U   .  
52   R  AN  A AS   CS CSF     G          PR  U   .  
53   S  AN  A AS   CS CSF     G          PR  U   .  
54   T  AN  A AS   CS CSF     G          PR  U   .  
55   U  AN  A AS   CS CSF     G          PR  U   .  
56   V  AN  A AS   CS CSF     G          PR  U   .  
57   W  AN  A AS   CS CSF     G          PR  U   .  
58   X  AN  A AS   CS CSF     G          PR  U   .  
59   Y  AN  A AS   CS CSF     G          PR  U   .  
5a   Z  AN  A AS   CS CSF     G          PR  U   .  
5b   [        AS              G    PU    PR      .  
5c   \        AS              G    PU    PR      .  
5d   ]        AS              G    PU    PR      .  
5e   ^        AS              G    PU    PR      .  
5f   _        AS   CS CSF     G    PU    PR      .  
60   `        AS              G    PU    PR      .  
61   a  AN  A AS   CS CSF     G  L       PR     X.  
62   b  AN  A AS   CS CSF     G  L       PR     X.  
63   c  AN  A AS   CS CSF     G  L       PR     X.  
64   d  AN  A AS   CS CSF     G  L       PR     X.  
65   e  AN  A AS   CS CSF     G  L       PR     X.  
66   f  AN  A AS   CS CSF     G  L       PR     X.  
67   g  AN  A AS   CS CSF     G  L       PR      .  
68   h  AN  A AS   CS CSF     G  L       PR      .  
69   i  AN  A AS   CS CSF     G  L       PR      .  
6a   j  AN  A AS   CS CSF     G  L       PR      .  
6b   k  AN  A AS   CS CSF     G  L       PR      .  
6c   l  AN  A AS   CS CSF     G  L       PR      .  
6d   m  AN  A AS   CS CSF     G  L       PR      .  
6e   n  AN  A AS   CS CSF     G  L       PR      .  
6f   o  AN  A AS   CS CSF     G  L       PR      .  
70   p  AN  A AS   CS CSF     G  L       PR      .  
71   q  AN  A AS   CS CSF     G  L       PR      .  
72   r  AN  A AS   CS CSF     G  L       PR      .  
73   s  AN  A AS   CS CSF     G  L       PR      .  
74   t  AN  A AS   CS CSF     G  L       PR      .  
75   u  AN  A AS   CS CSF     G  L       PR      .  
76   v  AN  A AS   CS CSF     G  L       PR      .  
77   w  AN  A AS   CS CSF     G  L       PR      .  
78   x  AN  A AS   CS CSF     G  L       PR      .  
79   y  AN  A AS   CS CSF     G  L       PR      .  
7a   z  AN  A AS   CS CSF     G  L       PR      .  
7b   {        AS              G    PU    PR      .  
7c   |        AS              G    PU    PR      .  
7d   }        AS              G    PU    PR      .  
7e   ~        AS              G    PU    PR      .  
7f            AS  C                              .  
```  
  
## 참고 항목  
 [문자 분류](../c-runtime-library/character-classification.md)   
 [로캘](../c-runtime-library/locale.md)   
 [setlocale, \_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [멀티바이트 문자 시퀀스 해석](../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [to 함수](../c-runtime-library/to-functions.md)