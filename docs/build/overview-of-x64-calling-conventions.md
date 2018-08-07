---
title: 간략하게 x64 호출 규칙 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a05db5eb-0844-4d9d-8b92-b1b2434be0ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb4071cd3223ad2ab073f84418e641b515c05112
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374910"
---
# <a name="overview-of-x64-calling-conventions"></a>x64 호출 규칙 개요
두 가지 중요 한 차이점 x86 및 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 는 64 비트 주소 지정 기능 및 범용 레지스터 16 64 비트의 단순 집합입니다. 확장 된 레지스터 집합, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 사용 하 여는 [__fastcall](../cpp/fastcall.md) 호출 규칙 및 RISC 기반 예외 처리 모델입니다. `__fastcall` 규칙 처음 네 개의 인수가 및 스택 프레임에 대 한 레지스터를 사용 하 여 추가 인수를 전달 합니다.  
  
 다음 컴파일러 옵션을 사용 하도록 응용 프로그램을 최적화 하는 데 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]:  
  
-   [/favor(아키텍처에 맞게 최적화)](../build/reference/favor-optimize-for-architecture-specifics.md)  
  
## <a name="calling-convention"></a>호출 규칙  
 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 기본적으로 4 개 레지스터 빠른 호출 규칙을 사용 하는 응용 프로그램 이진 인터페이스 ABI (). 호출 스택의 해당 레지스터를 저장 하려면 호출 수신자에 대 한 섀도 저장소 공간이 할당 됩니다. 함수 호출에 인수 및 해당 인수에 사용 되는 레지스터 간의 엄격한 한 일 대응이 됩니다. 8 바이트에 맞지 않으면 없거나 1, 2, 4 또는 8 바이트 하는 모든 인수는 참조로 전달 되어야 합니다. 여러 레지스터에는 하나의 인수를 분산 하지 않습니다. x87 레지스터 스택은 사용 되지 않습니다. 이 호출 수신자가 사용할 수 있습니다. 하지만 고려해 야 할 휘발성 함수 호출 간에 합니다. 모든 부동 소수점 작업은 수행 XMM 레지스터 16을 사용 하 여 합니다. 정수 인수는 RCX, RDX, R8 및 r 9 레지스터에 전달 됩니다. 부동 소수점 인수 XMM0L, XMM1L, XMM2L, 및 XMM3L에 전달 됩니다. 16 바이트 인수는 참조로 전달 됩니다. 매개 변수 전달에 자세히 설명 되어 [매개 변수 전달](../build/parameter-passing.md)합니다. 이 레지스터 외에도 RAX, r 10, R11, XMM4, 및 XMM5 휘발성 간주 됩니다. 다른 모든 레지스터 volatile이 아닌 경우 레지스터 사용에서 자세히 설명 되어 [사용 등록](../build/register-usage.md) 및 [호출자/호출 수신자 저장 레지스터](../build/caller-callee-saved-registers.md)합니다.  
  
 호출자에 게는 피호출자에 게 매개 변수에 대 한 공간을 할당 하는 일을 담당 하며 호출 수신자 많은 매개 변수를 사용 하지 않는 경우에 4 개 레지스터 매개 변수를 저장 하는 데 충분 한 공간을 할당 해야 항상 합니다. 프로토타입화 되지 않은 C 언어 함수와 vararg C/c + + 함수에 대 한 지원을 간단해 집니다. Vararg 또는 프로토타입화 되지 않은 함수에 대 한 모든 부동 소수점 값이 반드시 해당 하는 범용 레지스터에 복제 합니다. 처음 4 개 이상의 매개 변수를 호출 하기 전에 처음 4 개에 대 한 섀도 저장소 위에 스택에 저장 되어야 합니다. Vararg 함수 정보에서 확인할 수 있습니다 [Varargs](../build/varargs.md)합니다. 프로토타입화 되지 않은 함수 정보에 자세히 설명 되어 [프로토타입화 되지 않은 함수](../build/unprototyped-functions.md)합니다.  
  
## <a name="alignment"></a>맞춤  
 대부분의 구조체는 기본 맞춤에 따라 정렬 됩니다. 규칙의 예외로 스택 포인터 및 `malloc` 또는 `alloca` 메모리 성능을 향상 시키기 위해 16 바이트에 따라 정렬 됩니다. 16 바이트를 초과 맞춤은 수동으로 수행 해야 하지만 대부분의 코드에 대 한 작동 합니다 XMM 작업에 대 한 일반적인 맞춤 크기를 16 바이트 것입니다. 구조 레이아웃 및 정렬 하는 방법에 대 한 자세한 내용은 참조 [형식 및 저장소](../build/types-and-storage.md)합니다. 스택 레이아웃에 대 한 정보를 참조 하십시오. [스택 사용](../build/stack-usage.md)합니다.  
  
## <a name="unwindability"></a>Unwindability  
 리프 함수는 비휘발성 레지스터를 변경 하지 않는 함수. 비-리프 함수 지역 변수에 대 한 추가 스택 공간을 할당 하거나 함수를 호출 하 여 예를 들어 volatile이 아닌 RSP 변경 될 수 있습니다. 예외가 처리 될 때 비휘발성 레지스터를 복구 하려면 비-리프 함수 올바르게 임의의 명령에 함수를 해제 하는 방법을 설명 하는 정적 데이터와 함께 지정 해야 합니다. 이 데이터는로 저장 *pdata*, 또는 참조 프로시저 데이터를 *xdata*, 예외 데이터를 처리 합니다. xdata 해제 정보를 포함 하 고 추가 pdata 또는 예외 처리기 함수를 가리킬 수 있습니다. 프롤로그와 에필로그는 xdata에서 올바르게 설명할 수 있도록 고도로 제한 합니다. 스택 포인터 리프 함수 내에서 제외 하 고 프롤로그 또는 에필로그의 일부가 아닌 코드의 어느 지역에 16 바이트로 정렬 되어야 합니다. 단순히 시뮬레이트하여는 반환 되므로 pdata 및 xdata 필요 하지 않습니다. 리프 함수 해제 수 있습니다. 함수 프롤로그와 에필로그의 적절 한 구조에 대 한 세부 정보를 참조 하십시오. [프롤로그 및 에필로그](../build/prolog-and-epilog.md)합니다. 예외 처리 및 예외 처리 및 pdata 및 xdata의 해제 하는 방법에 대 한 자세한 내용은 참조 [예외 처리 (x64)](../build/exception-handling-x64.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [x64 소프트웨어 규칙](../build/x64-software-conventions.md)