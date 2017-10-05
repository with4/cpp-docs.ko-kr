---
title: "구조적된 예외 처리와 c + +를 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- C++ exception handling, mixed with SEH
- structured exception handling, with C++ exception handling
ms.assetid: ec34b528-8c26-4429-b24a-6a68553aaa91
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 8f9805479d7ee9589cfd0da8491b0344d0bd7de1
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="using-structured-exception-handling-with-c"></a>C++에서 구조적 예외 처리 사용
이러한 문서에 설명된 구조적 예외 처리는 C 및 C++ 소스 파일에서 작동합니다. 하지만 C++용으로 특별히 디자인되지 않았으므로 권장되지 않습니다. C++ 예외 처리를 사용하여 코드의 이식성이 향상되는지 확인할 수 있습니다. 또한 C++ 예외 처리 메커니즘은 모든 형식의 예외를 처리할 수 있다는 점에서 보다 유연합니다.  
  
 Microsoft C++는 이제 ANSI C++ 표준을 기반으로 C++ 예외 처리 모델을 지원합니다. 이 메커니즘은 스택 해제 중에 로컬 개체의 소멸을 자동으로 처리합니다. 내결함성이 있는 C++ 코드를 작성하는 경우 예외 처리를 구현하려면 구조적 예외 처리 대신 C++ 예외 처리를 사용하는 것이 좋습니다. C++ 컴파일러는 이러한 문서에 설명된 대로 구조적 예외 처리 구문을 지원하지만, 표준 C 컴파일러는 C++ 예외 처리 구문을 지원하지 않습니다. C + + 예외 처리에 대 한 자세한 내용은 참조 하십시오. [c + + 예외 처리](../cpp/cpp-exception-handling.md) 및 *Annotated c + + Reference Manual* 구성은 Margaret Ellis와 Bjarne stroustrup이 작성 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [구조적 예외 처리(C/C++)](../cpp/structured-exception-handling-c-cpp.md)
