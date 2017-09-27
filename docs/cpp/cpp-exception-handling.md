---
title: "C + + 예외 처리 | Microsoft Docs"
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
- C++ exception handling
- Visual C++, exception handling
ms.assetid: 65f80b44-9d0f-4d17-b910-07205a5c5c40
caps.latest.revision: 14
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
ms.openlocfilehash: 9e23f99ad4c2b2a1129fa318fe6960e1c08df21d
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="c-exception-handling"></a>C++ 예외 처리
C++ 언어에는 예외의 throw 및 catch를 기본적으로 지원합니다. C++에서 프로그래밍하는 경우 이 단원에서 설명한 대로 기본 제공 C++ 예외 지원을 거의 항상 사용해야 합니다.  
  
 C + +에서에서 예외 처리 코드를 사용 하려면 사용 [/EHsc](../build/reference/eh-exception-handling-model.md)합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 C++ 예외 처리에 대한 이 설명에는 다음이 포함됩니다.  
  
-   [Try, catch 및 throw 문](../cpp/try-throw-and-catch-statements-cpp.md)  
  
-   [Catch 블록 평가 방법](../cpp/how-catch-blocks-are-evaluated-cpp.md)  
  
-   [예외 및 스택 해제](../cpp/exceptions-and-stack-unwinding-in-cpp.md)  
  
-   [예외 사양](../cpp/exception-specifications-throw-cpp.md)  
  
-   [noexcept](../cpp/noexcept-cpp.md)  
  
-   [처리되지 않은 C++ 예외](../cpp/unhandled-cpp-exceptions.md)  
  
-   [C(구조적) 및 C++ 예외 혼합](../cpp/mixing-c-structured-and-cpp-exceptions.md)  
  
## <a name="support-for-earlier-mfc-exceptions"></a>이전 MFC 예외 지원  
 버전 4.0부터 MFC는 C++ 예외 처리 메커니즘을 사용합니다. 새 코드에서는 C++ 예외 처리를 사용하는 것이 좋지만 MFC 버전 4.0 이상은 기존 코드의 연결이 끊어지지 않도록 MFC의 이전 버전의 매크로를 유지합니다. 매크로 및 새 메커니즘도 결합할 수 있습니다. 내용 매크로 c + + 예외 처리 혼합 및 새로운 메커니즘을 사용 하도록 기존 코드를 변환에 대 한 문서를 참조 [예외: MFC 매크로 및 c + + 예외 사용](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) 및 [예외: MFC에서 변환 예외 매크로](../mfc/exceptions-converting-from-mfc-exception-macros.md)합니다. 이전 MFC 예외 매크로를 계속 사용하는 경우 C++ 예외 키워드로 평가합니다. 참조 [예외: 버전 3.0의에서 예외 매크로 변경 사항](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [예외 처리](../cpp/exception-handling-in-visual-cpp.md)
