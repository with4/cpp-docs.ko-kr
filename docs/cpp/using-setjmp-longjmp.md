---
title: Setjmp-longjmp 사용 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- longjmp_cpp
- setjmp_cpp
dev_langs:
- C++
helpviewer_keywords:
- C++ exception handling, setjmp/longjmp functions
- setjmpex.h
- longjmp function in C++ programs
- setjmp.h
- setjmp function
- setjmp function, C++ programs
ms.assetid: 96be8816-f6f4-4567-9a9c-0c3c720e37c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2073729fc5445fc36e3d8a6f52c4f69b079c8b47
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462133"
---
# <a name="using-setjmplongjmp"></a>setjmp/longjmp 사용
때 [setjmp](../c-runtime-library/reference/setjmp.md) 하 고 [longjmp](../c-runtime-library/reference/longjmp.md) 는 로컬이 아닌를 실행 하는 방법을 제공 함께 사용 하는 **goto**합니다. setjmp와 longjmp는 표준 호출이나 반환 규칙을 사용하지 않고 전에 호출된 루틴에서 오류 처리 또는 복구 코드에 실행 제어를 전달하는 데 주로 사용됩니다.  
  
> [!CAUTION]
>  그러나 때문 **setjmp** 하 고 **longjmp** c + + 개체 의미 체계를 지원 하지 않으며 지역 변수의 최적화를 막아 성능을 저하 시킬 수 있으므로, 사용 하지 않는 것이 좋습니다 c + + 프로그램에 해당 합니다. 사용 하는 것이 좋습니다 **시도**/**catch** 대신 생성 합니다.  
  
 사용 하려는 경우 **setjmp**/**longjmp** c + + 프로그램에 포함 \<setjmp.h > 또는 \<setjmpex.h > 간에 올바른 상호 작용이 보장에 함수 및 c + + 예외 처리 합니다. 사용 하는 경우 [/EH](../build/reference/eh-exception-handling-model.md) 스택 해제 중를 컴파일하려면 로컬 개체의 소멸자가 호출 됩니다. 사용 하는 경우 **/EHs** 컴파일 및 함수를 사용 하는 함수 호출 중에 [nothrow](../cpp/nothrow-cpp.md) 및 사용 하는 함수가 **nothrow** 호출 **longjmp**, 최적화 프로그램에 따라 소멸자가 해제 발생 하지 않을 수 있습니다.  
  
 이식 가능한 코드에서 로컬이 아닌 **goto** 를 호출 하는 **longjmp** 실행 되 면 잘못 프레임 기반 개체가 소멸 되지 않을 합니다.  
  
## <a name="see-also"></a>참고자료  
 [C(구조적) 및 C++ 예외 혼합](../cpp/mixing-c-structured-and-cpp-exceptions.md)