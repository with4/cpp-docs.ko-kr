---
title: "Catch 블록 평가 (c + +) 하는 방법 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- try-catch keyword [C++], catchable types
- catch keyword [C++], types of catch handlers
- C++ exception handling, catch handlers
- exception handling, catching and deleting exceptions
- types [C++], exception handling
ms.assetid: 202dbf07-8ace-4b3b-b3ae-4b45c275e0b4
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 744f75f86fd7d3e2ca2a2545a7914f923c4454b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-catch-blocks-are-evaluated-c"></a>Catch 블록 평가 방법 (C++)
일반적으로 std::exception에서 파생되는 형식을 throw할 것을 권장하지만 C++를 사용하면 모든 형식의 예외를 throw할 수 있습니다. c + + 예외를 낼 수 있습니다는 **catch** 나 어떤 형식의 예외를 catch 할 수 있는 처리기는 throw 된 예외와 같은 형식을 지정 하는 처리기.  
  
 throw된 예외의 형식이 하나의 기본 클래스 또는 여러 개의 클래스를 가진 클래스인 경우 예외 형식의 기본 클래스 및 예외 형식의 기본에 대한 참조를 허용하는 처리기로 catch할 수 있습니다. 예외가 참조에 의해 catch될 때 실제 throw된 예외 개체에 바인딩됩니다. 바인딩되지 않는 예외는 복사본입니다(함수에 대한 인수와 동일).  
  
 예외가 throw 되 면 다음과 같은 유형의로 걸러 질 수 있습니다 **catch** 처리기:  
  
-   줄임표 구문을 사용하여 모든 형식을 받아들일 수 있는 처리기.  
  
-   예외 개체와 동일한 형식을 허용 하는 처리기 복사 되었기 때문에 **const** 및 `volatile` 한정자는 무시 됩니다.  
  
-   예외 개체와 동일한 형식에 대한 참조를 허용하는 처리기.  
  
-   에 대 한 참조를 허용 하는 처리기는 **const** 또는 `volatile` 예외 개체와 동일한 유형의 형식이 있습니다.  
  
-   예외 개체와 동일한 형식의 기본 클래스를 허용 하는 처리기 한 복사본 이므로 **const** 및 `volatile` 한정자는 무시 됩니다. **catch** 기본 클래스에 대 한 처리기 앞에 오면 안 된 **catch** 파생된 클래스에 대 한 처리기입니다.  
  
-   예외 개체와 동일한 형식의 기본 클래스에 대한 참조를 허용하는 처리기.  
  
-   에 대 한 참조를 허용 하는 처리기는 **const** 또는 `volatile` 예외 개체와 동일한 형식의 기본 클래스의 형식입니다.  
  
-   throw된 포인터 개체가 표준 포인터 변환 규칙을 통해 변환될 수 있는 대상 포인터를 허용하는 처리기.  
  
 순서를 **catch** 처리기 중요는 표시 하기 때문에 대 한 처리기는 주어진 **시도** 블록 표시 되는 순서 대로 검사 됩니다. 예를 들어 파생 클래스의 처리기 앞에 기본 클래스의 처리기를 배치하면 오류가 발생합니다. 일치 하는 **catch** 처리기가 발견, 처리기 검사 하지 않습니다. 따라서 줄임표 **catch** 처리기에 대 한 마지막 처리기 여야 합니다 해당 **시도** 블록입니다. 예:  
  
```  
// ...  
try  
{  
    // ...  
}  
catch( ... )  
{  
    // Handle exception here.  
}  
// Error: the next two handlers are never examined.  
catch( const char * str )  
{  
    cout << "Caught exception: " << str << endl;  
}  
catch( CExcptClass E )  
{  
    // Handle CExcptClass exception here.  
}  
```  
  
 이 예제에서는 줄임표 **catch** 처리기를 검사 하는 유일한 처리기입니다.  
  
## <a name="see-also"></a>참고 항목  
 [C++ 예외 처리](../cpp/cpp-exception-handling.md)