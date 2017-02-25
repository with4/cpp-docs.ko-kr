---
title: "변환 연산자의 변경 내용 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "변환 연산자"
  - "변환, explicit"
  - "explicit 키워드[C++]"
  - "연산자[C++], 명시적 형식 변환"
  - "형식 변환, 명시적 변환"
ms.assetid: 9b83925c-71b7-4bd3-ac2e-843dd7c7f184
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 변환 연산자의 변경 내용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서는 변환 연산자의 구문이 Managed Extensions for C\+\+와 다르게 변경되었습니다.  
  
 `op_Implicit`를 작성하여 변환을 지정하는 경우를 예로 들 수 있습니다.  다음은 언어 사양에서 가져온 `MyDouble`의 정의입니다.  
  
```  
__gc struct MyDouble {  
   static MyDouble* op_Implicit( int i );   
   static int op_Explicit( MyDouble* val );  
   static String* op_Explicit( MyDouble* val );   
};  
```  
  
 즉, 정수의 경우 이 정수를 `MyDouble`로 변환하는 알고리즘은 `op_Implicit` 연산자에서 제공됩니다.  또한 이 변환은 컴파일러에서 암시적으로 수행됩니다.  마찬가지로, `MyDouble` 개체의 경우 두 `op_Explicit` 연산자는 해당 개체를 정수 또는 관리되는 `String` 엔터티로 변환하기 위한 알고리즘을 각각 제공합니다.  그러나 컴파일러는 사용자가 명시적으로 요청하지 않는 한 변환을 수행하지 않습니다.  
  
 C\#의 경우 이 예제는 다음과 같습니다.  
  
```  
class MyDouble {  
   public static implicit operator MyDouble( int i );   
   public static explicit operator int( MyDouble val );  
   public static explicit operator string( MyDouble val );   
};  
```  
  
 Managed Extensions for C\+\+보다 C\# 코드가 C\+\+와 더 비슷합니다.  새 구문에서는 그렇지 않습니다.  
  
 ISO\-C\+\+ 위원회에서는 예기치 않은 결과가 발생할 위험을 줄이기 위해 `explicit` 키워드를 도입했습니다. 예를 들어 차원으로 정수 인수 하나를 받는 `Array` 클래스에서는 모든 정수를 `Array` 개체로 암시적으로 변환하게 되지만 이 동작은 적절하지 않습니다.  이러한 문제를 방지하기 위한 방법 중 하나로 생성자에 두 번째 더미 인수를 사용하는 디자인 방식을 채택할 수 있습니다.  
  
 반면 C\+\+ 내에서 클래스 형식을 디자인할 때는 변환 쌍을 제공하지 말아야 합니다.  이를 보여 주는 좋은 예로 표준 문자열 클래스가 있습니다.  암시적 변환은 C 스타일 문자열을 사용하는 단일 인수 생성자입니다.  그러나 이는 문자열 개체를 C 스타일 문자열로 변환하는 암시적 변환 연산자를 제공하지 않으며 오히려 사용자가 명명된 함수\(이 경우 `c_str()`\)를 명시적으로 호출해야 합니다.  
  
 따라서 변환 연산자에 암시적\/명시적 동작을 연결하고 변환 집합을 단일 선언 형태로 캡슐화하면 원래 C\+\+의 변환 연산자 지원 기능이 향상될 것이므로, 결국 `explicit` 키워드가 도입되었습니다.  [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] 언어는 변환 연산자를 다음과 같이 지원합니다. 연산자의 기본 동작에 따라 변환 알고리즘이 암시적으로 적용되므로 이러한 방식은 C\#의 경우보다 다소 간편합니다.  
  
```  
ref struct MyDouble {  
public:  
   static operator MyDouble^ ( int i );  
   static explicit operator int ( MyDouble^ val );  
   static explicit operator String^ ( MyDouble^ val );  
};  
```  
  
 또 다른 변경 사항은 단일 인수 생성자가 `explicit`로 선언된 것처럼 취급한다는 점입니다.  즉, 해당 호출을 트리거하려면 명시적 캐스트가 필요합니다.  그러나 명시적 변환 연산자를 정의하면 단일 인수 생성자가 아닌 이 변환 연산자가 호출된다는 점에 주의해야 합니다.  
  
## 참고 항목  
 [클래스 또는 인터페이스 내에서 멤버 선언\(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)