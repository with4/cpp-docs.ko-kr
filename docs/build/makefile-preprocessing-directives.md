---
title: "메이크파일 전처리 지시문 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "!UNDEF"
  - "!INCLUDE"
  - "!IFNDEF"
  - "!MESSAGE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "!CMDSWITCHES 지시문"
  - "!ELSE 지시문"
  - "!ELSEIF 지시문"
  - "!ELSEIFDEF 지시문"
  - "!ELSEIFNDEF 지시문"
  - "!ENDIF 지시문"
  - "!ERROR 지시문"
  - "!IF 지시문"
  - "!IFDEF 지시문"
  - "!IFNDEF 지시문"
  - "!INCLUDE 지시문"
  - "!MESSAGE 지시문"
  - "!UNDEF 지시문"
  - "CMDSWITCHES 지시문"
  - "지시문, 메이크파일 전처리"
  - "ELSE 지시문"
  - "ELSEIF 지시문"
  - "ELSEIFDEF 지시문"
  - "ELSEIFNDEF 지시문"
  - "ENDIF 지시문"
  - "ERROR 지시문"
  - "IF 지시문"
  - "IFDEF 지시문"
  - "IFNDEF 지시문"
  - "INCLUDE 지시문"
  - "메이크파일, 전처리 지시문"
  - "MESSAGE 지시문"
  - "NMAKE 프로그램, 식"
  - "NMAKE 프로그램, 전처리기 지시문"
  - "전처리 지시문, 메이크파일"
  - "UNDEF 지시문"
ms.assetid: bcedeccb-d981-469d-b9e8-ab5d097fd8c2
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 메이크파일 전처리 지시문
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

전처리 지시문은 대\/소문자를 구분하지 않습니다.  맨 앞의 느낌표\(\!\)는 줄의 시작 부분에 표시되어야 합니다.  느낌표 뒤에 공백이나 탭을 0개 이상 표시하여 들여쓸 수 있습니다.  
  
 **\!CMDSWITCHES**  
 {**\+**&#124; **–**}*option*...  나열된 각 *option*을 설정 또는 해제합니다.  공백이나 탭은 \+나 – 연산자 앞에 표시해야 하며 연산자와 [옵션 문자](../build/nmake-options.md) 사이에는 표시할 수 없습니다.  옵션 문자는 대\/소문자를 구분하지 않으며 슬래시\( \/ \)를 사용하지 않고 지정합니다.  일부 옵션만 설정하고 나머지는 해제하려면 별도의 **\!CMDSWITCHES** 사양을 사용합니다.  
  
 메이크파일에는 \/D, \/I, \/N 및 \/S만 사용할 수 있습니다.  Tools.ini에는 \/F, \/HELP, \/NOLOGO, \/X 및 \/?를 제외한 모든 옵션을 사용할 수 있습니다.  설명 블록에 지정된 변경 내용은 다음 설명 블록 이후에 적용됩니다.  이 지시문은 **MAKEFLAGS**를 업데이트하므로 **MAKEFLAGS**가 지정된 경우 재귀하는 동안 변경 내용이 상속됩니다.  
  
 **\!ERROR**  *text*  
 오류 U1050에 *text*를 표시한 다음 NMAKE를 중지합니다. \/K, \/I, **.IGNORE**, **\!CMDSWITCHES** 또는 대시\(–\) 명령 한정자가 사용된 경우에도 적용됩니다.  *text* 앞에 사용된 공백이나 탭은 무시됩니다.  
  
 **\!MESSAGE**  *text*  
 *text*를 표준 출력에 표시합니다.  *text* 앞에 사용된 공백이나 탭은 무시됩니다.  
  
 **\!INCLUDE** \[**\<\<\]**filename*\[*\>**\>**\]  
 *filename*을 메이크파일로 읽은 다음 현재 메이크파일을 계속 처리합니다.  NMAKE는 먼저 현재 디렉터리나 지정된 디렉터리에서 *filename*을 찾은 다음 재귀적으로 모든 부모 메이크파일에서 찾습니다. 그런 다음 *filename*이 꺾쇠괄호\(\< \>\)로 묶여 있으면 \<\> **INCLUDE**매크로를 사용하여 지정한 디렉터리에서 찾습니다. 이 매크로는 처음에 INCLUDE 환경 변수로 설정됩니다.  이 지시문은 **.SUFFIXES** 설정, **.PRECIOUS** 및 유추 규칙을 재귀적 메이크파일로 전달하는 데 유용합니다.  
  
 **\!IF**  `constantexpression`  
 `constantexpression`이 0이 아닌 값으로 계산된 경우 **\!IF**와 다음 **\!ELSE** 또는 `!ENDIF` 사이의 문을 처리합니다.  
  
 **\!IFDEF**  *macroname*  
 *macroname*이 정의된 경우 `!IFDEF`와 다음 **\!ELSE** 또는 `!ENDIF` 사이의 문을 처리합니다.  null 매크로는 정의된 것으로 간주합니다.  
  
 **\!IFNDEF**  *macroname*  
 *macroname*이 정의되지 않은 경우 **\!IFNDEF**와 다음 **\!ELSE** 또는 `!ENDIF` 사이의 문을 처리합니다.  
  
 **\!ELSE**\[**IF** *constantexpression* &#124; **IFDEF** *macroname*&#124; **IFNDEF** *macroname*\]  
 이전 **\!IF**, `!IFDEF` 또는 **\!IFNDEF** 문이 0으로 계산된 경우 **\!ELSE**와 다음 `!ENDIF` 사이의 문을 처리합니다.  선택적 키워드를 사용하면 전처리를 다양하게 제어할 수 있습니다.  
  
 **\!ELSEIF**  
 **\!ELSE IF**의 동의어입니다.  
  
 **\!ELSEIFDEF**  
 **\!ELSE IFDEF**의 동의어입니다.  
  
 **\!ELSEIFNDEF**  
 **\!ELSE IFNDEF**의 동의어입니다.  
  
 `!ENDIF`  
 **\!IF**, `!IFDEF` 또는 **\!IFNDEF** 블록의 끝을 표시합니다.  같은 줄에서 `!ENDIF` 뒤에 오는 텍스트는 무시됩니다.  
  
 **\!UNDEF**  *macroname*  
 *macroname*을 정의하지 않습니다.  
  
## 참고 항목  
 [메이크파일 전처리](../build/makefile-preprocessing.md)