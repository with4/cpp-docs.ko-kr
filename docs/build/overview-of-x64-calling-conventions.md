---
title: "x64 호출 규칙 개요 | Microsoft Docs"
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
ms.assetid: a05db5eb-0844-4d9d-8b92-b1b2434be0ea
caps.latest.revision: 12
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# x64 호출 규칙 개요
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

x86과 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 사이에 수정된 두 가지 중요한 사항은 64비트 주소 지정 기능과 일반적인 용도를 위한 16가지 64비트 레지스터의 단순 집합입니다.  확장된 레지스터 집합의 경우 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]는 [\_\_fastcall](../cpp/fastcall.md) 호출 규칙과 RISC 기반 예외 처리 모델만 사용합니다.  `__fastcall` 모델에서는 처음 네 개의 인수에 대해 레지스터를 사용하고 다른 매개 변수를 전달하는 데는 스택 프레임을 사용합니다.  
  
 다음 컴파일러 옵션을 사용하면 응용 프로그램을 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]에 대해 최적화할 수 있습니다.  
  
-   [\/favor\(아키텍처에 맞게 최적화\)](../build/reference/favor-optimize-for-architecture-specifics.md)  
  
## 호출 규칙  
 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] ABI\(응용 프로그램 이진 인터페이스\)는 해당 레지스터에 대한 스택 백이 포함된 4개의 레지스터 빠른 호출 규칙입니다.  함수의 인수와 해당 인수의 레지스터 사이에는 엄격한 일대일 대응 관계가 있습니다.  8바이트에 맞지 않거나 1, 2, 4 또는 8바이트가 아닌 모든 인수는 참조로 전달해야 합니다.  여러 레지스터 간에 단일 인수가 공용으로 사용되지도 않습니다.  x87 레지스터 스택은 사용되지 않습니다.  이를 사용할 수는 있지만 함수 호출 간에 volatile로 간주해야 합니다.  모든 부동 소수점 연산은 16 XMM 레지스터를 사용하여 수행합니다.  인수는 레지스터 RCX, RDX, R8 및 R9에 전달됩니다.  인수가 float\/double인 경우 이러한 인수는 XMM0L, XMM1L, XMM2L 및 XMM3L에 전달됩니다.  16바이트 인수는 참조로 전달됩니다.  매개 변수 전달에 대한 자세한 내용은 [매개 변수 전달](../build/parameter-passing.md)을 참조하십시오.  이러한 레지스터 이외에 RAX, R10, R11, XMM4 및 XMM5는 volatile입니다.  다른 모든 레지스터는 비volatile입니다.  레지스터 사용에 대한 자세한 내용은 [레지스터 사용](../build/register-usage.md) 및 [호출자\/호출 수신자 저장 레지스터](../build/caller-callee-saved-registers.md)를 참조하십시오.  
  
 호출자는 호출 수신자에 매개 변수를 할당하기 위한 공간을 마련합니다. 호출자는 호출 수신자에 필요한 매개 변수 수가 더 적더라도 4개의 레지스터 매개 변수에 충분한 공간을 항상 할당해야 합니다.  이렇게 하면 프로토타입화되지 않은 C 함수와 vararg C\/C\+\+ 함수를 쉽게 지원할 수 있습니다.  vararg 또는 프로토타입화되지 않은 함수의 경우 모든 부동 소수점 값을 상응하는 일반 용도의 레지스터에 복제해야 합니다.  처음 4개 이후의 모든 매개 변수는 처음 4개 매개 변수를 위한 백업 저장소 위쪽의 스택에, 호출보다 앞에 저장되어야 합니다.  vararg 함수에 대한 자세한 내용은 [Varargs](../build/varargs.md)를 참조하십시오.  프로토타입화되지 않은 함수에 대한 자세한 내용은 [프로토타입화되지 않은 함수](../build/unprototyped-functions.md)를 참조하십시오.  
  
## 맞춤  
 대부분의 구조체는 기본 맞춤에 따라 정렬됩니다.  이 규칙의 예외로는 성능을 향상시키기 위해 16바이트로 정렬되는 malloc 또는 alloca 메모리와 스택 포인터가 있습니다.  16바이트를 초과하는 맞춤은 수동으로 수행해야 하지만 16바이트는 XMM 연산에 일반적인 맞춤 크기이므로 대부분의 코드에 충분합니다.  구조체 레이아웃과 맞춤에 대한 자세한 내용은 [형식 및 저장소](../build/types-and-storage.md)를 참조하십시오.  스택 레이아웃에 대한 자세한 내용은 [스택 사용](../build/stack-usage.md)을 참조하십시오.  
  
## 해제  
 모든 리프 함수\(함수를 호출하지도 않고 스택 공간을 직접 할당하지도 않는 함수\)는 비volatile 레지스터를 복구할 수 있도록 이를 올바르게 해제하는 방법을 운영 체제에 알리는 데이터\(xdata 또는 ehdata라고 하며 pdata에서 가리키는 데이터\)를 사용하여 주석 처리해야 합니다.  프롤로그와 에필로그는 매우 제한적이므로 xdata에서 올바르게 설명할 수 있습니다.  리프 함수의 경우를 제외하고 스택 포인터는 에필로그나 프롤로그의 일부가 아닌 코드의 모든 영역에서 16바이트로 정렬해야 합니다.  함수 프롤로그와 에필로그의 올바른 구조에 대한 자세한 내용은 [프롤로그 및 에필로그](../build/prolog-and-epilog.md)를 참조하십시오.  예외 처리 및 예외 처리\/해제 pdata와 xdata에 대한 자세한 내용은 [예외 처리\(x64\)](../build/exception-handling-x64.md)를 참조하십시오.  
  
## 참고 항목  
 [x64 소프트웨어 규칙](../build/x64-software-conventions.md)