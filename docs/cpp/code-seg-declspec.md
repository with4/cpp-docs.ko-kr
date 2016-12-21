---
title: "code_seg (__declspec) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "code_seg_cpp"
  - "code_seg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "code_seg __declspec 키워드"
ms.assetid: ad3c1105-15d3-4e08-b7b9-e4bd9d7b6aa0
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# code_seg (__declspec)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 `code_seg` 선언 속성은 함수 또는 클래스 멤버 함수의 개체 코드가 저장될 .obj 파일의 실행 텍스트 세그먼트의 이름을 지정합니다.  
  
## 구문  
  
```  
__declspec(code_seg("segname")) declarator  
```  
  
## 설명  
 `__declspec(code_seg(...))` 특성을 사용하면 메모리에 개별적으로 페이징 또는 잠글 수 있는 별도의 명명된 세그먼트에 코드를 배치할 수 있습니다.  이 특성을 사용하여 인스턴스화한 템플릿과 컴파일러에서 생성된 코드의 배치를 제어할 수 있습니다.  
  
 *세그먼트*는 메모리에 하나의 단위로 로드된 .obj 파일의 명명된 데이터 블록입니다.  *텍스트 세그먼트*는 실행 코드가 포함된 세그먼트입니다.  *섹션*이라는 용어는 종종 세그먼트와 같은 의미로 사용됩니다.  
  
 `declarator`가 지정될 때 생성되는 개체 코드는 좁은 문자열 리터럴인 `segname`에서 지정한 텍스트 세그먼트에 배치됩니다.  `segname`라는 이름은 [섹션](../preprocessor/section.md) pragma에 지정되지 않아도 선언에 사용할 수 있습니다.  기본적으로 `code_seg`가 지정되지 않으면 개체 코드가 .text라는 세그먼트에 배치됩니다.  `code_seg` 특성은 기존의 모든 [\#pragma code\_seg](../preprocessor/code-seg.md) 지시문을 재정의합니다.  멤버 함수에 적용된 `code_seg` 특성은 바깥쪽 클래스에 적용되는 모든 `code_seg` 특성을 재정의합니다.  
  
 엔터티에 `code_seg` 특성이 있는 경우 같은 엔터티의 모든 선언 및 정의가 `code_seg` 특성과 동일해야 합니다.  기본 클래스에 `code_seg` 특성이 있는 경우 파생된 클래스는 특성이 동일해야 합니다.  
  
 `code_seg` 특성이 네임스페이스 범위 함수 또는 멤버 함수에 적용되면 해당 함수의 개체 코드가 지정된 텍스트 세그먼트에 배치됩니다.  이 특성이 클래스에 적용되면 컴파일러 생성 특수 멤버 함수를 포함하는 클래스와 중첩된 클래스의 모든 멤버 함수가 지정된 세그먼트에 배치됩니다.  멤버 함수 본문에 정의된 클래스 등 로컬 정의 클래스는 바깥쪽 범위의 `code_seg` 특성을 상속하지 않습니다.  
  
 `code_seg` 특성이 템플릿 클래스 또는 템플릿 함수에 적용되면 템플릿의 모든 암시적 특수화가 지정된 세그먼트에 배치됩니다.  명시적 또는 부분적 특수화는 기본 템플릿에서 `code_seg` 특성을 상속하지 않습니다.  특수화에 같거나 다른 `code_seg` 특성을 지정할 수 있습니다.  `code_seg` 특성은 명시적 템플릿 인스턴스화에 적용할 수 없습니다.  
  
 기본적으로 특수 멤버 함수 등 컴파일러에서 생성된 코드는 .text 세그먼트에 배치됩니다.  `#pragma code_seg` 지시문은 이 기본값을 재정의하지 않습니다.  컴파일러에서 생성된 코드가 배치되는 제어에 클래스, 클래스 템플릿 또는 함수 템플릿의 `code_seg` 특성을 사용합니다.  
  
 람다는 바깥쪽 범위에서 `code_seg` 특성을 상속합니다.  람다에 대한 세그먼트를 지정하려면 매개 변수 선언 절 뒤와 변경 가능한 변수 또는 예외, 모든 후행 반환 형식 사양 및 람다 본문 앞에 `code_seg` 특성을 적용합니다.  자세한 내용은 [람다 식 구문](../cpp/lambda-expression-syntax.md)을 참조하십시오.  이 예제에서는 PagedMem이라는 세그먼트에 람다를 정의합니다.  
  
```cpp  
auto Sqr = [](int t) __declspec(code_seg("PagedMem")) -> int { return t*t; };  
```  
  
 여러 세그먼트에 특정 멤버 함수, 특히 가상 멤버 함수를 배치할 때 주의해야 합니다.  기본 클래스 메서드가 페이징되지 않은 세그먼트에 상주할 때 페이징된 세그먼트에 상주하는 파생된 클래스에 가상 함수를 정의하는 경우 다른 기본 클래스 메서드 또는 사용자 코드는 가상 메서드를 호출해도 페이지 오류가 트리거되지 않는다고 가정할 수 있습니다.  
  
## 예제  
 이 예제에서는 암시적 및 명시적 템플릿 특수화를 사용할 때 `code_seg` 특성이 세그먼트 배치를 제어하는 방법을 보여 줍니다.  
  
```  
// code_seg.cpp  
// Compile: cl /EHsc /W4 code_seg.cpp  
  
// Base template places object code in Segment_1 segment  
template<class T>  
class __declspec(code_seg("Segment_1")) Example  
{  
public:  
   virtual void VirtualMemberFunction(T /*arg*/) {}  
};  
  
// bool specialization places code in default .text segment  
template<>  
class Example<bool>   
{  
public:  
   virtual void VirtualMemberFunction(bool /*arg*/) {}  
};  
  
// int specialization places code in Segment_2 segment  
template<>  
class __declspec(code_seg("Segment_2")) Example<int>   
{  
public:  
   virtual void VirtualMemberFunction(int /*arg*/) {}  
};  
  
// Compiler warns and ignores __declspec(code_seg("Segment_3"))  
// in this explicit specialization  
__declspec(code_seg("Segment_3")) Example<short>; // C4071  
  
int main()  
{  
   // implicit double specialization uses base template's  
   // __declspec(code_seg("Segment_1")) to place object code  
   Example<double> doubleExample{};  
   doubleExample.VirtualMemberFunction(3.14L);  
  
   // bool specialization places object code in default .text segment  
   Example<bool> boolExample{};  
   boolExample.VirtualMemberFunction(true);  
  
   // int specialization uses __declspec(code_seg("Segment_2"))  
   // to place object code  
   Example<int> intExample{};  
   intExample.VirtualMemberFunction(42);  
}  
```  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)