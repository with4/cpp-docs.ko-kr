---
title: ARM 어셈블리 지시문 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
dev_langs:
- C++
ms.assetid: 9cfa8896-ec10-4e77-855a-3135c40d7d2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9f5ab97fb9ccdff19206b829383c622efd3f7921
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="arm-assembler-directives"></a>ARM 어셈블리 지시문
Microsoft ARM 어셈블러의 7 장에에서 설명 되어 있는 ARM 어셈블리 언어를 사용 하는 대부분의 경우는 [ARM 어셈블러 도구 가이드](http://go.microsoft.com/fwlink/p/?linkid=246102)합니다. 그러나 일부 어셈블리 지시문의 Microsoft 구현 ARM 어셈블리 지시문에서 다릅니다. 이 문서에서는 차이점을 설명 합니다.  
  
## <a name="microsoft-implementations-of-arm-assembly-directives"></a>ARM 어셈블리 지시문의 Microsoft 구현  
 영역  
 Microsoft ARM 어셈블러 이러한 영역 특성을 지원: 맞춤, 코드, CODEALIGN, 데이터, NOINIT, READONLY, READWRITE, 엄지 단추, ARM입니다.  
  
 에 설명 된 대로 작동 엄지와 ARM 제외한 모든 페이지는 [ARM 어셈블러 도구 가이드](http://go.microsoft.com/fwlink/p/?linkid=246102)합니다.  
  
 Microsoft ARM 어셈블러 엄지 단추는 코드 섹션 Thumb 코드가 포함 되어 하는 코드 섹션에 대 한 기본값을 나타냅니다.  ARM은 ARM 코드 섹션에 포함 되어 있음을 나타냅니다.  
  
 ATTR  
 지원되지 않습니다.  
  
 CODE16  
 Microsoft ARM 어셈블러에서 허용 하지 않는 이전 UAL Thumb 구문을 의미 하기 때문에 지원 되지 않습니다.  UAL 구문과 함께 THUMB 지시문을 대신 사용 합니다.  
  
 일반적인  
 공통 영역에 대 한 맞춤의 사양을 지원 되지 않습니다.  
  
 DCDO  
 지원되지 않습니다.  
  
 DN QN, SN  
 형식 또는 레지스터 별칭에 레인의 사양을 지원 되지 않습니다.  
  
 항목  
 지원되지 않습니다.  
  
 EQU  
 사양으로 정의 된 기호에 대 한 형식의 지원 되지 않습니다.  
  
 내보내기 및 전역  
 ```  
EXPORTsym {[type]}  
```  
  
 `sym` 가 기호를 내보낼 수 있습니다.  `[type]`를 지정 수 있습니다 `[DATA]` 기호 데이터를 가리키는지 나타내기 위해 또는 `[FUNC]` 코드 가리키는 기호를 나타냅니다.  
  
 전역는 내보내기에 대 한 동의어입니다.  
  
 EXPORTAS  
 지원되지 않습니다.  
  
 프레임  
 지원되지 않습니다.  
  
 함수 및 프로시저  
 Assembly 구문은 사용자 지정의 사양을 지원 하지만 있는 저장 호출자와 호출 수신자 저장 레지스터를 나열 하 여 프로시저에 대 한 호출 규칙 Microsoft ARM 어셈블러 구문 자격 레지스터 목록을 무시 합니다.  어셈블러에 의해 생성 된 디버그 정보는 기본 호출 규칙을 지원 합니다.  
  
 가져오기 및 EXTERN  
 ```  
IMPORT sym{, WEAK alias{, TYPE t}}  
```  
  
 `sym` 가져올 기호 이름이입니다.  
  
 약한 경우 `alias` 의미 지정 된 `sym` 약한 external입니다. 에 대 한 정의가 없습니다. 링크 타임에 없는 경우 모든 참조를 바인딩할 대신 `alias`합니다.  
  
 경우 형식 `t` 을 지정할 경우 `t` 링커에서 확인을 시도 하는지는 어떻게 나타냅니다 `sym`합니다.  이러한 값에 대 한 `t` 가능 합니다.   
1-라이브러리 검색을 수행 하지 않습니다 `sym`  
2-라이브러리 검색 `sym`  
3-`sym` 별칭인 `alias` (기본값)  
  
 EXTERN는 점을 제외 하 고 가져오기에 대 한 동의어 `sym` 현재 어셈블리에서에 대 한 참조가 있는 경우에 가져올 합니다.  
  
 MACRO  
 매크로의 상태 코드를 보유할 변수를 사용 하는 지원 되지 않습니다. 매개 변수는 지원 되지 않습니다 매크로 대 한 기본 값입니다.  
  
 NOFP  
 지원되지 않습니다.  
  
 선택 하 고, TTL, SUBT  
 Microsoft ARM 어셈블러 목록을 생성 하지 않으므로 때문에 지원 되지 않습니다.  
  
 PRESERVE8  
 지원되지 않습니다.  
  
 재배치  
 `RELOC n` 명령 또는 데이터 정의 지침에 따라만 수 있습니다. "익명 기호가 없습니다" 된 배치할 수 있습니다.  
  
 필요  
 지원되지 않습니다.  
  
 REQUIRE8  
 지원되지 않습니다.  
  
 THUMBX  
 Microsoft ARM 어셈블러 Thumb 2EE 명령 집합을 지원 하지 않으므로 지원 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [ARM 어셈블러 명령줄 참조](../../assembler/arm/arm-assembler-command-line-reference.md)   
 [ARM 어셈블러 진단 메시지](../../assembler/arm/arm-assembler-diagnostic-messages.md)