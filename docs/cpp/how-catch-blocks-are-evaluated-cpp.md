---
title: "Catch 블록 평가 방법 (C++) | Microsoft Docs"
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
  - "C++ 예외 처리, catch 처리기"
  - "catch 키워드[C++], catch 처리기의 형식"
  - "예외 처리, 예외 catch 및 삭제"
  - "try-catch 키워드[C++], catch할 수 있는 형식"
  - "형식[C++], 예외 처리"
ms.assetid: 202dbf07-8ace-4b3b-b3ae-4b45c275e0b4
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Catch 블록 평가 방법 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

일반적으로 std::exception에서 파생되는 형식을 throw할 것을 권장하지만 C\+\+를 사용하면 모든 형식의 예외를 throw할 수 있습니다.  C\+\+ 예외는 throw된 예외와 같은 형식을 지정하는 **catch** 처리기 또는 모든 형식의 예외를 catch할 수 있는 처리기로 catch할 수 있습니다.  
  
 throw된 예외의 형식이 하나의 기본 클래스 또는 여러 개의 클래스를 가진 클래스인 경우 예외 형식의 기본 클래스 및 예외 형식의 기본에 대한 참조를 허용하는 처리기로 catch할 수 있습니다.  예외가 참조에 의해 catch될 때 실제 throw된 예외 개체에 바인딩됩니다. 바인딩되지 않는 예외는 복사본입니다\(함수에 대한 인수와 동일\).  
  
 예외가 throw되면 다음 형식의 **catch** 처리기에서 catch할 수 있습니다.  
  
-   줄임표 구문을 사용하여 모든 형식을 받아들일 수 있는 처리기.  
  
-   예외 개체와 동일한 형식을 허용하는 처리기. 이 처리기는 복사본이므로 **const** 및 `volatile` 한정자는 무시됩니다.  
  
-   예외 개체와 동일한 형식에 대한 참조를 허용하는 처리기.  
  
-   예외 개체와 동일한 형식의 **const** 또는 `volatile`에 대한 참조를 허용하는 처리기.  
  
-   예외 개체와 동일한 형식의 기본 클래스를 허용하는 처리기. 이 처리기는 복사본이므로 **const** 및 `volatile` 한정자는 무시됩니다.  기본 클래스의 **catch** 처리기는 파생 클래스의 **catch** 처리기 앞에 오면 안 됩니다.  
  
-   예외 개체와 동일한 형식의 기본 클래스에 대한 참조를 허용하는 처리기.  
  
-   예외 개체와 동일한 형식의 기본 클래스의 **const** 또는 `volatile`에 대한 참조를 허용하는 처리기입니다.  
  
-   throw된 포인터 개체가 표준 포인터 변환 규칙을 통해 변환될 수 있는 대상 포인터를 허용하는 처리기.  
  
 지정된 **try** 블록의 **catch** 처리기는 표시된 순서대로 검사되므로 처리기의 표시 순서가 중요합니다.  예를 들어 파생 클래스의 처리기 앞에 기본 클래스의 처리기를 배치하면 오류가 발생합니다.  일치하는 **catch** 처리기가 발견되면 처리기 검사는 더 이상 진행되지 않습니다.  따라서 줄임표 **catch** 처리기는 **try** 블록의 마지막 처리기여야 합니다.  예를 들면 다음과 같습니다.  
  
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
  
 이 예제에서 검사된 처리기는 줄임표 **catch** 처리기뿐입니다.  
  
## 참고 항목  
 [C\+\+ 예외 처리](../cpp/cpp-exception-handling.md)