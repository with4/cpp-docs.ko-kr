---
title: "메이크파일 전처리 지시문 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- '!UNDEF'
- '!INCLUDE'
- '!IFNDEF'
- '!MESSAGE'
dev_langs: C++
helpviewer_keywords:
- ERROR directive
- '!MESSAGE directive'
- IF directive
- '!UNDEF directive'
- IFDEF directive
- '!ELSEIF directive'
- '!IFDEF directive'
- '!IF directive'
- UNDEF directive
- '!CMDSWITCHES directive'
- ENDIF directive
- directives, makefile preprocessing
- INCLUDE directive
- IFNDEF directive
- preprocessing directives, makefiles
- '!IFNDEF directive'
- ELSEIFNDEF directive
- NMAKE program, expressions
- ELSEIF directive
- '!ERROR directive'
- '!ENDIF directive'
- MESSAGE directive
- '!INCLUDE directive'
- '!ELSEIFNDEF directive'
- CMDSWITCHES directive
- '!ELSEIFDEF directive'
- '!ELSE directive'
- NMAKE program, preprocessor directives
- makefiles, preprocessing directives
- ELSE directive
- ELSEIFDEF directive
ms.assetid: bcedeccb-d981-469d-b9e8-ab5d097fd8c2
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1bc73a86b0772b13731aaf7ac4e2ef0760caa8a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="makefile-preprocessing-directives"></a>메이크파일 전처리 지시문
전처리 지시문은 대/소문자 구분 하지 않습니다. 느낌표 (!)은 줄의 시작 부분에 표시 되어야 합니다. 공백이 나 탭을 0 이상 들여쓰기에 느낌표 뒤에 나타날 수 있습니다.  
  
 **! CMDSWITCHES**  
 {**+**&#124;  **-** }*옵션*... 각 설정 *옵션* 또는 해제를 나열 합니다. 공백이 나 탭 앞에 나와야 합니다는 + 또는-현재 연산자 연산자 사이 나타날 수 없음 및 [문자 옵션](../build/nmake-options.md)합니다. 문자는 대/소문자 구분 하지 않으며 없이 슬래시 (/)가 지정 되었습니다. 일부 옵션을 지정 하 고 나머지는 해제를 설정 하려면 별도 사양에 사용 하 여 **! CMDSWITCHES**합니다.  
  
 만 /D, I, /N 및 /S 메이크파일의 사용할 수 있습니다. Tools.ini에서 모든 옵션은 /F, /HELP, /NOLOGO를 제외 하 고 허용/X, 및 /?. 설명 블록에 지정 된 변경 내용이 적용 될 때까지 다음 설명 블록 하지 않습니다. 이 지시어 업데이트 **MAKEFLAGS**; 재귀 하는 동안 변경 내용을 상속 되므로 경우 **MAKEFLAGS** 지정 됩니다.  
  
 **! 오류***텍스트*   
 표시 *텍스트* 오류 U1050, 다음 NMAKE, 중단 되어도에 /K / I, **합니다. 무시**, **! CMDSWITCHES**, 또는 대시 (-) 명령 한정자 사용 됩니다. 공백 또는 탭 하기 전에 *텍스트* 무시 됩니다.  
  
 **! 메시지***텍스트*   
 표시 *텍스트* 을 표준 출력 합니다. 공백 또는 탭 하기 전에 *텍스트* 무시 됩니다.  
  
 **! 포함**[  **\<** ] *filename*[  **>** ]  
 읽고 *filename* 을 메이크파일으로 현재 메이크파일을 계속 합니다. Nmake는 *filename* 먼저 지정 된 열 또는 현재 디렉터리에서 다음 재귀적으로 모든 부모 메이크파일에 그런 다음 경우 *filename* 꺾쇠 괄호로 묶여 (\<>), 지정 된 경로에 **포함** 매크로 처음에 INCLUDE 환경 변수 설정 합니다. 이 지시문은 **합니다. 접미사** 설정, **합니다. 소중한**, 및 유추 규칙을 재귀 메이크파일입니다.  
  
 **! IF**  `constantexpression`  
 이전 **! IF** 와 다음 **! 다른** 또는 `!ENDIF` 경우 `constantexpression` 0이 아닌 값으로 계산 합니다.  
  
 **! IFDEF***매크로 이름*   
 이전 `!IFDEF` 와 다음 **! 다른** 또는 `!ENDIF` 경우 *매크로 이름* 정의 됩니다. Null 매크로 정의로 간주 됩니다.  
  
 **! IFNDEF***매크로 이름*   
 이전 **! IFNDEF** 와 다음 **! 다른** 또는 `!ENDIF` 경우 *매크로 이름* 정의 되어 있지 않습니다.  
  
 **! 다른**[**IF** *constantexpression* &#124; **IFDEF** *매크로 이름*&#124; **IFNDEF** *매크로 이름*]  
 이전 **! 다른** 와 다음 `!ENDIF` 경우 이전 **! IF**, `!IFDEF`, 또는 **! IFNDEF** 문을 처리 합니다. 선택적 키워드 게 전처리 제어할 수 있습니다.  
  
 **! ELSEIF**  
 에 대 한 동의어 **! ELSE IF**합니다.  
  
 **! ELSEIFDEF**  
 에 대 한 동의어 **! 다른 IFDEF**합니다.  
  
 **! ELSEIFNDEF**  
 에 대 한 동의어 **! ELSE IFNDEF**합니다.  
  
 `!ENDIF`  
 끝을 표시 한 **! IF**, `!IFDEF`, 또는 **! IFNDEF** 블록입니다. 같은 줄에서 `!ENDIF` 같은 줄에는 무시 됩니다.  
  
 **! UNDEF***매크로 이름*   
 정의 해제 *매크로 이름*합니다.  
  
## <a name="see-also"></a>참고 항목  
 [메이크파일 전처리](../build/makefile-preprocessing.md)