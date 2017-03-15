---
title: "/Zc:rvalueCast(형식 변환 규칙 적용) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "rvaluecast"
  - "/Zc:rvalueCast"
  - "VC.Project.VCCLCompilerTool.EnforceTypeConversionRules"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc 컴파일러 옵션(C++)"
  - "형식 변환 규칙 적용"
  - "rvaluecast"
  - "Zc 컴파일러 옵션(C++)"
  - "-Zc 컴파일러 옵션(C++)"
ms.assetid: 7825277d-e565-4c48-b0fb-76ac0b0c6e38
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /Zc:rvalueCast(형식 변환 규칙 적용)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/Zc:rvalueCast** 옵션을 지정하면 컴파일러에서는 C\+\+11 표준에 따라 캐스트 연산의 결과로 rvalue 참조 형식을 올바르게 식별합니다.  이 옵션이 지정되지 않은 경우 컴파일러 동작은 Visual Studio 2012와 동일합니다.  기본적으로 **\/Zc:rvalueCast**는 OFF로 설정됩니다.  캐스트 사용 시 준수 및 오류 제거를 위해 **\/Zc:rvalueCast**를 사용하는 것이 좋습니다.  
  
## 구문  
  
```  
/Zc:rvalueCast[-]  
```  
  
## 설명  
 **\/Zc:rvalueCast**를 지정하면 컴파일러는 C\+\+11 표준의 섹션 5.4에 따라 비참조 형식을 결과로 반환하는 캐스트 식과 rvalue 형식으로 비함수 형식에 대한 rvalue 참조를 결과로 반환하는 캐스트 식만 처리합니다.  기본적으로 또는 **\/Zc:rvalueCast\-**를 지정한 경우 컴파일러는 비호환적이고 rvalue 참조를 결과로 반환하는 모든 캐스트 식을 rvalue로 처리합니다.  
  
 rvalue 참조 형식을 사용하는 함수에 캐스트 식을 인수로 전달하는 경우 **\/Zc:rvalueCast**를 사용합니다.  컴파일러가 캐스트 식의 형식을 잘못 결정하면 기본 동작으로 인해 컴파일러 오류 [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md)가 발생합니다.  다음 예제는 \/Zc:rvalueCast를 지정하지 않은 경우 올바른 코드에서 발생한 컴파일러 오류를 보여줍니다.  
  
```cpp  
// Test of /Zc:rvalueCast  
// compile by using:  
// cl /c /Zc:rvalueCast- make_thing.cpp  
// cl /c /Zc:rvalueCast make_thing.cpp  
  
#include <utility>  
  
template <typename T>   
struct Thing {  
   // Construct a Thing by using two rvalue reference parameters  
   Thing(T&& t1, T&& t2)  
      : thing1(t1), thing2(t2) {}  
  
   T& thing1;  
   T& thing2;  
};  
  
// Create a Thing, using move semantics if possible  
template <typename T>  
Thing<T> make_thing(T&& t1, T&& t2)  
{  
   return (Thing<T>(std::forward<T>(t1), std::forward<T>(t2)));  
}  
  
struct Test1 {  
   long a;  
   long b;  
  
   Thing<long> test() {   
      // Use identity casts to create rvalues as arguments  
      return make_thing(static_cast<long>(a), static_cast<long>(b));   
   }  
};  
  
```  
  
 보고하지 않는 것이 적절한 경우 기본 컴파일러 동작이 오류 C2102를 보고하지 않을 수도 있습니다.  다음 예제에서 **\/Zc:rvalueCast**를 지정하지 않은 경우 ID 캐스트에서 만든 rvalue 주소가 사용되면 컴파일러는 오류를 보고하지 않습니다.  
  
```cpp  
int main() {  
   int a = 1;  
   int *p = &a;   // Okay, take address of lvalue   
                  // Identity cast creates rvalue from lvalue;    
   p = &(int)a;   // problem: should cause C2102: '&' requires l-value  
}  
```  
  
 Visual C\+\+의 규칙과 관련된 문제에 대한 자세한 내용은 [비표준 동작](../../cpp/nonstandard-behavior.md)을 참조하세요.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 선택합니다.  
  
3.  **명령줄** 속성 페이지를 선택합니다.  
  
4.  **\/Zc:rvalueCast**를 포함하도록 **추가 옵션** 속성을 수정한 다음 **확인**을 선택합니다.  
  
## 참고 항목  
 [\/Zc\(규칙\)](../../build/reference/zc-conformance.md)