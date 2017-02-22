---
title: "인라인 어셈블리에서 레지스터 사용 및 유지 | Microsoft Docs"
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
  - "__asm 키워드[C++], 레지스터 값"
  - "인라인 어셈블리, 레지스터"
  - "레지스터 유지"
  - "레지스터, 인라인 어셈블리"
ms.assetid: dbcd7360-6f3e-4b22-9ee2-9f65ca6f2543
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 인라인 어셈블리에서 레지스터 사용 및 유지
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft 관련  
 일반적으로 가정 하지 않아야 레지스터 값을 지정된 해야 해야 한다는 경우는  `__asm`블록을 시작 합니다.  레지스터 값은 별도 보존 아닙니다  `__asm`블록.  인라인 코드 블록을 종료 하 고 다른 시작 하는 경우 레지스터의 첫 번째 블록에서 해당 값을 유지 하려면 두 번째 블록에서 사용할 수 없습니다.   `__asm`블록 값 결과 정상적인 제어 흐름에 상관 없이 등록을 상속 합니다.  
  
 사용 하는 경우는  `__fastcall`호출 규칙을 컴파일러가 함수 인수 전달 대신 레지스터에서 스택에.  이 함수를 사용 하 여 문제를 일으킬 수  `__asm`함수에는 매개 변수는 레지스터에는 구분할 방법이 없기 때문에 차단 합니다.  함수 매개 변수는 EAX에서 받을 발생 즉시 다른 EAX에 저장을 원래 매개 변수가 손실 됩니다.  ECX 레지스터를 사용 하 여 선언 된 함수를 유지 해야 하는 또한  `__fastcall`.  
  
 충돌을 피하기 위해 이러한 레지스터를 사용 하지 마십시오의  `__fastcall`규칙을 포함 하는 함수는  `__asm`블록.  지정 하는 경우는  `__fastcall`규칙 \/Gr 컴파일러 옵션을 사용 하 여 전역으로 선언 모든 함수를 포함 하는  `__asm`블록  `__cdecl`또는   `__stdcall`.  \(에서  `__cdecl`해당 함수의 C 호출 규칙을 사용 하 여 컴파일러가 특성.\) \/Gr을 사용 하 여 컴파일하지 않습니다 경우 사용 하 여 함수를 선언 하지는  `__fastcall`특성.  
  
 사용 하는 경우  `__asm`어셈블리 언어의 C\/c \+ \+ 함수를 작성 하려면 EAX, EBX, ECX, EDX, ESI, 또는 EDI 레지스터를 유지할 필요가 없습니다.  POWER2 예를 들어,에서.C 예제에서  [쓰기 함수의 인라인 어셈블리를 사용 하 여](../../assembler/inline/writing-functions-with-inline-assembly.md),  `power2`함수는 EAX 레지스터의 값을 유지 하지 합니다.  그러나 이러한 레지스터를 사용 하는 품질에 영향을 코드 레지스터 할당 기에서 값을 저장 하는 데 사용할 수 없습니다 때문에  `__asm`블록.  또한 인라인 어셈블리 코드에서 EBX, ESI, EDI를 사용 하 여 저장 하 고 함수 프롤로그와 에필로그에 해당 레지스터를 복원할 컴파일러를 강제로 있습니다.  
  
 \(DS, SS, SP, BP, 플래그 레지스터 등\) 사용 하 여 다른 레지스터의 범위를 유지 해야 하면  `__asm`블록.  \(예를 들어, 스택 전환\)을 변경 하려면 몇 가지 이유가 없다면 ESP와 EBP 레지스터를 보존 해야 합니다.  참고  [인라인 어셈블리 최적화](../../assembler/inline/optimizing-inline-assembly.md).  
  
 SSE 유형도 스택 할당을 동적 코드를 생성 하는 컴파일러가 스택의 8 바이트 정렬을 해야 합니다.  정렬 후 로컬 변수와 함수 매개 변수에 액세스할 수 있도록 컴파일러 두 프레임 포인터를 유지 합니다.  프레임 포인터 생략 \(FPO\)를 수행 하는 컴파일러가 EBP 및 ESP를 사용 합니다.  컴파일러가 FPO 수행 하지 않으면, EBX와 EBP를 사용 합니다.  코드가 실행 제대로 수정 하지 마십시오 EBX asm 코드에서 프레임 포인터를 수정할 수 동적 스택 할당 함수에 필요 합니다.  8 바이트 정렬된 형식을 함수를 외부로 이동 하거나 EBX 사용 하지 마십시오.  
  
> [!NOTE]
>  방향 플래그가 STD 또는 CLD 명령을 사용 하 여 인라인 어셈블리 코드가 변경 되 면 플래그가 원래 값으로 복원 해야 합니다.  
  
 **Microsoft 특정 끝**  
  
## 참고 항목  
 [인라인 어셈블러](../../assembler/inline/inline-assembler.md)