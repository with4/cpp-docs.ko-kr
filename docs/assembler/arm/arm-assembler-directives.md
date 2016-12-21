---
title: "ARM Assembler Directives | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 9cfa8896-ec10-4e77-855a-3135c40d7d2a
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ARM Assembler Directives
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

대부분의 경우 문서화의 7 장 ARM 어셈블리 언어 Microsoft ARM 어셈블러를 사용 하는 [ARM 어셈블러 도구 가이드](http://go.microsoft.com/fwlink/?LinkId=246102).  그러나 일부 어셈블리 지시문의 Microsoft 구현 ARM 어셈블리 지시문에서 다.  이 문서에서는 차이점을 설명 합니다.  
  
## ARM 어셈블리 지시문의 Microsoft 구현  
 영역  
 이러한 지역 특성 ARM Microsoft 어셈블러를 지원: 맞춤, 코드, CODEALIGN, 데이터, NOINIT, READONLY, READWRITE, 엄지, 팔.  
  
 엄지와 암을 제외한 모든에서 설명 하는 대로 작업을 [ARM 어셈블러 도구 가이드](http://go.microsoft.com/fwlink/?LinkId=246102).  
  
 ARM Microsoft 어셈블러에서 엄지 코드 섹션 Thumb 코드를 포함 하 고 기본 코드 섹션을 나타냅니다.  ARM은 ARM 코드 섹션이 나타냅니다.  
  
 ATTR  
 지원되지 않습니다.  
  
 CODE16  
 Microsoft ARM 어셈블러에서는 허용 되지 않는 전 UAL 엄지 구문, 의미 하는 것 때문에 없습니다.  엄지 지시문 대신 UAL 구문을 함께 사용 하.  
  
 일반적인  
 일반적인 영역에 대 한 맞춤 사양에서 지원 되지 않습니다.  
  
 DCDO  
 지원되지 않습니다.  
  
 DN, QN, SN  
 형식 또는 별칭 레지스터에는 레인 사양에서 지원 되지 않습니다.  
  
 항목  
 지원되지 않습니다.  
  
 EQU  
 사양에 정의 된 기호에 대해 종류를 지원 하지 않습니다.  
  
 내보내기 및 글로벌  
 ```  
  
EXPORTsym {[type]}  
  
```  
  
 `sym`기호를 내보낼 수 있습니다.  `[type]`을 하나 지정 하는 경우 발생할 수 있습니다 `[DATA]` 기호에 대 한 데이터를 가리키는 것을 나타내기 위해 또는 `[FUNC]` 기호 코드를 가리키는 것을 나타냅니다.  
  
 동의어에 대 한 내보내기 전역적입니다.  
  
 EXPORTAS  
 지원되지 않습니다.  
  
 프레임  
 지원되지 않습니다.  
  
 함수 및 프로시저  
 호출자가 저장 하 고 있는 호출 수신자 저장 레지스터 목록을 작성 하 여 프로시저에서 호출 하는 규칙의 사용자 지정 어셈블리 구문을 지원 하지만 ARM Microsoft 어셈블러 구문을 허용 하지만 레지스터 목록을 무시 합니다.  어셈블러에 의해 생성 된 디버그 정보가 기본 호출 규칙을 지원 합니다.  
  
 가져오기 및 EXTERN  
 ```  
  
IMPORT sym{, WEAK alias{, TYPE t}}  
  
```  
  
 `sym`가져올 심볼의 이름이입니다.  
  
 약한 경우 `alias` 지정이 나타냅니다 `sym` 는 약한 외부입니다.  링크 시 그에 대 한 정의가 없습니다 찾을 수 다음에 대 한 모든 참조를 대신 바인딩할 경우 `alias`.  
  
 경우 형식  `t` 에 지정 된 다음 `t` 어떻게 링커가 해결 하 려 해야 `sym`.  이러한 값에 대 한 `t` 수 있습니다.   
1\-라이브러리 검색을 수행 하지 마십시오`sym`   
2\-의 라이브러리 검색`sym`   
3\-`sym` 에 대 한 별칭입니다 `alias` \(기본값\)  
  
 EXTERN 이거나, 가져오기에 대 한 동의어는 제외 하 고 `sym` 현재 어셈블리에서 참조를 경우에 가져와집니다.  
  
 매크로  
 매크로의 조건 코드를 보유 하는 변수를 사용할 수 없습니다.  기본값은 매크로 매개 변수는 지원 되지 않습니다.  
  
 NOFP  
 지원되지 않습니다.  
  
 최적, TTL, SUBT  
 Microsoft ARM 어셈블러 목록을 얻을 수 없는 때문에 없습니다.  
  
 PRESERVE8  
 지원되지 않습니다.  
  
 재배치  
 `RELOC n`명령 또는 데이터 정의 지시문을 따를 수 있습니다.  "재배치 될 수 없는 익명 기호"입니다.  
  
 필요  
 지원되지 않습니다.  
  
 REQUIRE8  
 지원되지 않습니다.  
  
 THUMBX  
 Microsoft ARM 어셈블러 엄지 2EE 명령 집합을 지원 하지 않으므로 지원 되지 않습니다.  
  
## 참고 항목  
 [ARM Assembler Command\-Line Reference](../../assembler/arm/arm-assembler-command-line-reference.md)   
 [ARM Assembler Diagnostic Messages](../../assembler/arm/arm-assembler-diagnostic-messages.md)