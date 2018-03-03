---
title: __thiscall | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __thiscall
- __thiscall_cpp
dev_langs:
- C++
helpviewer_keywords:
- __thiscall keyword [C++]
ms.assetid: a6a22dd2-0101-4885-b33b-22f6057965df
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a55f7d288758b345dfc4f182f2153e0d39a1b349
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="thiscall"></a>__thiscall
## <a name="microsoft-specific"></a>Microsoft 전용  
 `__thiscall` 및 멤버 함수에 사용 되며 가변 인수를 사용 하지 않는 c + + 멤버 함수에 의해 사용 되는 기본 호출 규칙은 호출 규칙입니다. 아래 `__thiscall`, 호출 수신자에 대 한 가능 하지 않은 스택을 정리 `vararg` 함수입니다. 인수를 오른쪽에서 왼쪽으로 스택에서 푸시되는 `this` x86 스택 아니라에 ECX 레지스터를 통해 전달 되 고 포인터 아키텍처.  
  
 사용 하는 한 가지 이유 `__thiscall` 클래스 멤버를 가진 함수는 사용 중인 `__clrcall` 기본적으로 합니다. 이 경우 사용할 수 있습니다 `__thiscall` 있도록 개별 멤버 함수의 네이티브 코드에서 호출할 수 있습니다.  
  
 로 컴파일할 때 [/clr: pure](../build/reference/clr-common-language-runtime-compilation.md), 모든 함수 및 함수 포인터는 `__clrcall` 달리 지정 되지 않은 합니다. **/clr:pure** 및 **/clr:safe** 컴파일러 옵션은 Visual Studio 2015에서는 더 이상 사용되지 않습니다.  
  
 Visual c + + 2005 이전 버전에서 thiscall 호출 규칙 수 지정 되지 않았습니다. 명시적으로 프로그램에서 때문에 `thiscall` 키워드가 없습니다.  
  
 `vararg`멤버 함수는 사용 된 `__cdecl` 호출 규칙입니다. 와 모든 함수 인수는 스택에서 푸시됩니다는 `this` 포인터 마지막 스택에 배치  
  
 C + +에만 이러한 호출 규칙 적용 되므로 C 이름 데코레이션 구성표가 없습니다.  
  
 ARM의 및 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 컴퓨터 `__thiscall` 허용 되 고 컴파일러에서 무시 합니다.  
  
 비정적 클래스 함수의 경우 함수가 아웃오브 라인으로 정의되면 호출 규칙 한정자를 아웃오브 라인 정의에서 지정하지 않아도 됩니다. 즉, 클래스 비정적 멤버 메서드의 경우 선언하는 동안 지정된 호출 규칙이 정의 시 가정됩니다.  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [인수 전달 및 명명 규칙](../cpp/argument-passing-and-naming-conventions.md)