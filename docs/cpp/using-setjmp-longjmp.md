---
title: "Setjmp longjmp 사용 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- longjmp_cpp
- setjmp_cpp
dev_langs: C++
helpviewer_keywords:
- C++ exception handling, setjmp/longjmp functions
- SETJMPEX.H
- longjmp function in C++ programs
- SETJMP.H
- setjmp function
- setjmp function, C++ programs
ms.assetid: 96be8816-f6f4-4567-9a9c-0c3c720e37c5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 80b134942cf5670527d75b94f2af4847e421c3b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="using-setjmplongjmp"></a>setjmp/longjmp 사용
때 [setjmp](../c-runtime-library/reference/setjmp.md) 및 [longjmp](../c-runtime-library/reference/longjmp.md) 는 로컬이 아닌를 실행 하는 방법을 제공 함께 사용할 `goto`합니다. setjmp와 longjmp는 표준 호출이나 반환 규칙을 사용하지 않고 전에 호출된 루틴에서 오류 처리 또는 복구 코드에 실행 제어를 전달하는 데 주로 사용됩니다.  
  
> [!CAUTION]
>  그러나 `setjmp` 및 `longjmp`는 C++ 개체 의미 체계를 지원하지 않으며 지역 변수의 최적화를 막아 성능을 저하시킬 수 있으므로 C++ 프로그램에서는 사용하지 않는 것이 좋습니다. 사용 하는 것이 좋습니다 `try` / `catch` 대신 생성 합니다.  
  
 사용 하려는 경우 `setjmp` / `longjmp` c + + 프로그램에서 SETJMP도 포함 합니다. H 또는 SETJMPEX 합니다. 함수 및 c + + 예외 처리 간에 올바른 상호 작용이을 H. 사용 하는 경우 [/EH](../build/reference/eh-exception-handling-model.md) 를 컴파일하려면 로컬 개체에 대 한 소멸자가 스택 해제 중 호출 됩니다. 사용 하는 경우 **/EHs** 컴파일과 함수 호출 사용 하는 함수 중 하나를 [nothrow](../cpp/nothrow-cpp.md) 및 사용 하는 함수의 `nothrow` 호출 `longjmp`, 소멸자가 해제 하지 발생할 수 있으며, 그런 다음 최적화 프로그램에 따라.  
  
 이식 가능한 코드에서 `goto`를 호출하는 비로컬 `longjmp`가 실행되면 프레임 기반 개체가 제대로 삭제되지 않을 수도 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [C(구조적) 및 C++ 예외 혼합](../cpp/mixing-c-structured-and-cpp-exceptions.md)