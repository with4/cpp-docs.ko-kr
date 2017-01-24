---
title: "인수 전달 및 명명 규칙 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "인수 전달[C++], 규칙"
  - "인수[C++], 명명"
  - "인수[C++], 전달"
  - "인수[C++], 확장"
  - "코딩 규칙, 인수"
  - "규칙[C++], 인수 이름"
  - "명명 규칙[C++], 인수"
  - "인수 전달, 규칙"
  - "레지스터, 반환 값"
  - "thiscall 키워드[C++]"
ms.assetid: de468979-eab8-4158-90c5-c198932f93b9
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 인수 전달 및 명명 규칙
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 Visual C\+\+ 컴파일러에서는 함수와 호출자 간에 인수와 반환 값을 전달하기 위한 규칙을 지정할 수 있습니다.  지원되는 모든 플랫폼에서 모든 규칙을 사용할 수 있는 것은 아니며, 일부 규칙은 플랫폼별 구현을 사용합니다.  대부분의 경우 특정 플랫폼에서 지원되지 않는 규칙을 지정하는 키워드 또는 컴파일러 스위치는 무시되며 플랫폼 기본 규칙이 사용됩니다.  
  
 x86 플랫폼에서 모든 인수는 전달될 때 32비트로 확장됩니다.  반환 값도 32비트로 확장되며 EDX:EAX 레지스터 쌍에서 반환되는 8바이트 구조체를 제외하고 EAX 레지스터에서 반환됩니다.  더 큰 구조체는 숨겨진 반환 구조체에 대한 포인터로 EAX 레지스터에서 반환됩니다.  매개 변수는 오른쪽에서 왼쪽으로 스택에 푸시됩니다.  POD가 아닌 구조체는 레지스터에서 반환되지 않습니다.  
  
 컴파일러는 ESI, EDI, EBX 및 EBP 레지스터가 함수에서 사용되는 경우 이러한 레지스터를 저장하고 복원하는 프롤로그 및 에필로그 코드를 생성합니다.  
  
> [!NOTE]
>  구조체, 공용 구조체 또는 클래스가 값으로 함수에서 반환되는 경우 형식의 모든 정의가 동일해야 하며, 그렇지 않으면 프로그램이 런타임에 실패할 수 있습니다.  
  
 사용자 고유의 함수 프롤로그 및 에필로그 코드를 정의하는 방법에 대한 자세한 내용은 [Naked 함수 호출](../cpp/naked-function-calls.md)을 참조하십시오.  
  
 x64 플랫폼을 대상으로 하는 코드의 기본 호출 규칙에 대한 자세한 내용은 [x64 호출 규칙 개요](../build/overview-of-x64-calling-conventions.md)를 참조하십시오.  ARM 플랫폼을 대상으로 하는 코드의 호출 규칙 문제에 대한 자세한 내용은 [일반적인 Visual C\+\+ ARM 마이그레이션 문제](../build/common-visual-cpp-arm-migration-issues.md)를 참조하십시오.  
  
 다음과 같은 호출 규칙이 Visual C\/C\+\+ 컴파일러에서 지원됩니다.  
  
|키워드|스택 정리|매개 변수 전달|  
|---------|-----------|--------------|  
|[\_\_cdecl](../cpp/cdecl.md)|호출자|매개 변수를 스택에 역순으로\(오른쪽에서 왼쪽으로\) 푸시합니다.|  
|[\_\_clrcall](../cpp/clrcall.md)|해당 없음|CLR 식 스택에 매개 변수를 순서대로\(왼쪽에서 오른쪽으로\) 로드합니다.|  
|[\_\_stdcall](../cpp/stdcall.md)|호출 수신자|매개 변수를 스택에 역순으로\(오른쪽에서 왼쪽으로\) 푸시합니다.|  
|[\_\_fastcall](../cpp/fastcall.md)|호출 수신자|레지스터에 저장된 다음 스택에 푸시됩니다.|  
|[\_\_thiscall](../cpp/thiscall.md)|호출 수신자|스택에 푸시됩니다. **this** 포인터가 ECX에 저장됩니다.|  
|[\_\_vectorcall](../cpp/vectorcall.md)|호출 수신자|레지스터에 저장된 다음 스택에 역순으로\(오른쪽에서 왼쪽으로\) 푸시됩니다.|  
  
 관련 내용은 [사용되지 않는 호출 규칙](../cpp/obsolete-calling-conventions.md)을 참조하십시오.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [호출 규칙](../cpp/calling-conventions.md)