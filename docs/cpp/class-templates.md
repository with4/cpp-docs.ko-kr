---
title: "클래스 템플릿 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "클래스 템플릿"
  - "클래스[C++], 형식에 대해 작업"
  - "템플릿, 클래스 템플릿"
ms.assetid: 633a53c8-24ee-4c23-8c88-e7c3cb0b7ac3
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 클래스 템플릿
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

클래스 템플릿을 사용하여 형식에 대해 작동하는 클래스 패밀리를 만들 수 있습니다.  클래스 템플릿은 매개 변수가 있는 형식입니다.  클래스 템플릿은 전달된 매개 변수\(템플릿 인수\)의 가능한 값 각각에 대해 별도의 클래스를 만들 수 있음을 암시합니다.  
  
 템플릿 인수는 형식 또는 지정한 형식의 상수 값일 수 있습니다.  예를 들면 다음과 같습니다.  
  
```  
// class_templates.cpp  
template <class T, int i> class TempClass   
{  
public:  
    TempClass( void );  
    ~TempClass( void );  
    int MemberSet( T a, int b );  
private:  
    T Tarray[i];  
    int arraysize;  
};  
  
int main()  
{  
}  
```  
  
 이 예제에서 템플릿 클래스는 `T` 형식 및 int `i`라는 두 매개 변수를 사용합니다.  `T` 매개 변수에는 구조체 및 클래스를 비롯한 모든 형식을 전달할 수 있습니다.  `i` 매개 변수에는 정수 상수를 전달해야 합니다.  `i`는 컴파일 타임에 정의되는 상수이므로 표준 배열 선언을 사용하여 `i` 크기의 멤버 배열을 정의할 수 있습니다.  
  
 자세한 내용은 다음을 참조하십시오.  
  
-   [클래스 템플릿의 멤버](../Topic/Members%20of%20Class%20Templates.md)  
  
-   [클래스 멤버의 템플릿](../Topic/Templates%20for%20Class%20Members.md)  
  
-   [템플릿 클래스의 멤버 함수](../Topic/Member%20Functions%20of%20Template%20Classes.md)  
  
-   [중첩된 클래스 템플릿](../Topic/Nested%20Class%20Templates.md)  
  
-   [클래스 템플릿 인스턴스화](../Topic/Class%20Template%20Instantiation.md)  
  
-   [클래스 템플릿의 명시적 특수화](../Topic/Explicit%20Specialization%20of%20Class%20Templates.md)  
  
-   [클래스 템플릿의 부분 특수화](../cpp/template-specialization-cpp.md)  
  
-   [클래스 템플릿의 기본 인수](../Topic/Default%20Arguments%20for%20Class%20Templates.md)  
  
-   [템플릿 friend](../cpp/template-friends.md)  
  
## 참고 항목  
 [템플릿](../cpp/templates-cpp.md)