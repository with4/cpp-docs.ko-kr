---
title: "NMAKE 옵션 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NMAKE 프로그램, 옵션"
ms.assetid: 00ba1aec-ef27-44cf-8d82-c5c095e45bae
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# NMAKE 옵션
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 표에서는 NMAKE 옵션에 대하여 설명합니다.  옵션은 앞에 슬래시\(\/\)나 대시\(\-\)가 오고 대\/소문자를 구분하지 않습니다.  메이크파일이나 Tools.ini의 옵션 설정을 변경하려면 [메이크파일 전처리 지시문](../build/makefile-preprocessing-directives.md)을 사용합니다.  
  
|옵션|용도|  
|--------|--------|  
|\/A|종속 파일에 대하여 오래되지 않은 경우에도 계산된 모든 대상을 빌드합니다.  관련이 없는 대상은 빌드하지 않습니다.|  
|\/B|타임스탬프가 일치하는 경우에도 빌드합니다.  매우 빠른 시스템\(해상도가 2초 이하인 경우\)에서만 사용할 것을 권장합니다.|  
|\/C|심각하지 않은 NMAKE 오류나 경고, 타임스탬프 및 NMAKE 저작권 메시지를 비롯한 기본 출력을 억제합니다 .  \/K를 사용하면 경고가 발생하지 않습니다.|  
|\/D|대상이 없는 경우 계산된 각 대상과 종속 파일의 타임스탬프 및 메시지를 표시합니다.  메이크파일 디버깅에 \/P와 함께 사용하면 유용합니다.  **\!CMDSWITCHES**를 사용하여 메이크파일의 일부에 대해 \/D를 설정하거나 지웁니다.|  
|\/E|환경 변수가 메이크파일 매크로 정의를 재정의합니다.|  
|\/ERRORREPORT\[NONE &#124; PROMPT &#124; QUEUE &#124; SEND \]|런타임에 nmake.exe가 실행되지 않하면 \/ERRORREPORT를 사용하여 이러한 내부 오류에 대한 정보를 Microsoft에 보낼 수 있습니다.<br /><br /> \/ERRORREPORT에 대한 자세한 내용은 [\/errorReport\(내부 컴파일러 오류 보고\)](../build/reference/errorreport-report-internal-compiler-errors.md)를 참조하십시오.|  
|\/F `filename`|`filename`을 메이크파일로 지정합니다.  `filename` 앞에 공백이나 탭이 올 수 있습니다.  \/F는 각 메이크파일에 한 번씩 지정합니다.  표준 입력으로 메이크파일을 제공하려면 `filename`에 대시\(–\)를 지정하고 F6 키나 Ctrl\+Z를 사용하여 키보드 입력을 끝냅니다.|  
|\/G|\!INCLUDE 지시문에 포함된 메이크파일을 표시합니다.  자세한 내용은 [메이크파일 전처리 지시문](../build/makefile-preprocessing-directives.md)을 참조하십시오.|  
|\/HELP, \/?|NMAKE 명령줄 구문을 간략하게 요약하여 표시합니다.|  
|\/I|모든 명령의 종료 코드를 무시합니다.  메이크파일의 일부에 대해 \/I를 설정하거나 지우려면 **\!CMDSWITCHES**를 사용합니다.  메이크파일의 일부에 대하여 종료 코드를 무시하려면 대시\(–\) 명령 한정자나 [.IGNORE](../build/dot-directives.md)를 사용합니다.  두 가지 모두 지정된 경우 \/K를 재정의합니다.|  
|\/K|명령이 오류를 반환하는 경우 관련되지 않은 종속 줄 빌드를 계속합니다.  또한 경고를 발생시키고 종료 코드 1을 반환합니다.  기본적으로 명령이 0이 아닌 종료 코드를 반환하면 NMAKE가 중지됩니다.  \/K를 사용한 경우 발생하는 경고는 \/C를 사용하여 억제합니다. 두 가지 모두 지정된 경우 \/I는 \/K를 재정의합니다.|  
|\/N|명령을 표시만 하고 실행하지 않습니다. 전처리 명령은 실행됩니다.  재귀적 NMAKE 호출에는 명령을 표시하지 않습니다.  메이크파일 디버깅과 타임스탬프 확인에 유용합니다.  메이크파일의 일부에 대해 \/N을 설정하거나 지우려면 **\!CMDSWITCHES**를 사용합니다.|  
|\/NOLOGO|NMAKE 저작권 메시지를 표시하지 않습니다.|  
|\/P|표준 출력에 매크로 정의, 유추 규칙, 대상, [.SUFFIXES](../build/dot-directives.md) 목록 등의 정보를 표시한 다음 빌드를 실행합니다.  메이크파일이나 명령줄 대상이 없는 경우에는 정보만 표시합니다.  메이크파일을 디버깅하려면 \/D와 함께 사용합니다.|  
|\/Q|대상의 타임스탬프만 확인하고 빌드는 실행하지 않습니다.  모든 대상이 최신 상태이면 종료 코드 0을 반환하고 최신 상태가 아닌 대상이 있으면 0이 아닌 종료 코드를 반환합니다.  전처리 명령은 실행됩니다.  배치 파일에서 NMAKE를 실행하는 경우에 유용합니다.|  
|\/R|**.SUFFIXES** 목록을 지우고 Tools.ini 파일에 정의되어 있거나 미리 정의된 유추 규칙과 매크로를 무시합니다.|  
|\/S|실행된 명령을 표시하지 않습니다.  메이크파일의 일부를 표시하지 않으려면 **@** 명령 한정자나 [.SILENT](../build/dot-directives.md)를 사용합니다.  메이크파일의 일부에 대해 \/S를 설정하거나 지우려면 **\!CMDSWITCHES**를 사용합니다.|  
|\/T|명령줄 대상\(또는 첫 번째 메이크파일 대상\)의 타임스탬프를 업데이트하고 전처리 명령을 실행하지만 빌드는 실행하지 않습니다.|  
|\/U|\/N과 함께 사용해야 합니다.  \/N 출력을 배치 파일로 사용할 수 있도록 인라인 NMAKE 파일을 덤프합니다.|  
|\/X `filename`|NMAKE 오류 출력을 표준 오류 대신 `filename`으로 보냅니다.  `filename` 앞에 공백이나 탭이 올 수 있습니다.  오류 출력을 표준 출력으로 보내려면 `filename`에 대시\(–\)를 지정합니다.  명령에서 표준 오류로 보내는 출력에는 적용되지 않습니다.|  
|\/Y|일괄 처리 모드 유추 규칙을 사용하지 않습니다.  이 옵션을 선택하면 모든 일괄 처리 모드 유추 규칙이 일반 유추 규칙으로 처리됩니다.|  
  
## 참고 항목  
 [NMAKE 실행](../build/running-nmake.md)