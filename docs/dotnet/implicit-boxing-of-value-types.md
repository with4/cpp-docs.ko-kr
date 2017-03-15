---
title: "값 형식 명시적 boxing | Microsoft Docs"
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
  - "__box 키워드"
  - "boxing"
  - "boxing, __box 키워드"
  - "boxing, Visual C++"
  - "값 형식, Boxed"
ms.assetid: 9597c92f-a3fe-44af-ad80-f9d656847a35
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 값 형식 명시적 boxing
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서는 값 형식의 boxing이 Managed Extensions for C\+\+와 다르게 변경되었습니다.  
  
 이전에는 언어를 디자인하면서 기능을 사용하는 실제 경험 대신 원리적인 입장을 더 강조했습니다.  유사한 예로 원래 다중 상속 언어 디자인에서 Stroustrup은 가상 기본 클래스 하위 개체를 파생 클래스 생성자 내에서 초기화할 수 없도록 결정했으며 그에 따라 가상 기본 클래스로 사용되는 모든 클래스는 기본 생성자를 정의해야만 했습니다.  이후의 모든 가상 파생 클래스에서 호출되는 것은 바로 이 기본 생성자입니다.  
  
 가상 기본 클래스 계층 구조의 문제는 이후의 각 파생에 공유되는 가상 하위 개체 시프트를 초기화해야 한다는 데 있습니다.  예를 들어, 초기화에 버퍼 할당이 필요한 기본 클래스를 정의하는 경우 이 버퍼의 사용자 지정 크기가 생성자에 대한 인수로 전달될 수 있습니다.  그런 다음 `inputb`와 `outputb`라는 두 개의 가상 파생을 제공하면 각 클래스는 기본 클래스 생성자에 대한 특정 값을 제공합니다.  이제 `inputb` 및 `outputb`에서 모두 `in_out` 클래스를 파생하면 공유된 가상 기본 클래스 하위 개체에 대한 어떠한 값도 올바르게 계산할 수 없습니다.  
  
 따라서 원래 언어 디자인에서 Stroustrup은 파생 클래스 생성자의 멤버 초기화 목록 내에서 가상 기본 클래스를 명시적으로 초기화할 수 없도록 규정했습니다.  이렇게 하면 문제는 해결되지만 가상 기본 클래스의 초기화를 디렉션하는 것이 실제로는 불가능했습니다.  nihcl이라는 SmallTalk 컬렉션 라이브러리의 프리웨어 버전을 만든 National Institute of Health의 Keith Gorlen은 Stroustrup이 더 융통성 있는 언어 디자인을 개발하게끔 확신을 심어 준 주요 인물이었습니다.  
  
 개체 지향 계층 구조의 디자인 원칙에 따르면 파생 클래스는 해당 직접 기본 클래스의 비전용 구현에만 관련되어야 합니다.  가상 상속에 대한 융통성 있는 초기화 디자인을 지원하기 위해 Stroustrup은 이 원칙을 깨뜨려야 했습니다.  계층 구조의 최대 파생 클래스는 계층 구조 내에서의 위치와 상관없이 모든 가상 하위 개체 초기화를 담당합니다.  예를 들어, `inputb`와 `outputb`는 모두 해당 직접 가상 기본 클래스를 명시적으로 초기화합니다.  `in_out`이 `inputb`와 `outputb`에서 모두 파생되는 경우 `in_out`은 일단 제거된 가상 기본 클래스의 초기화를 담당하고 `inputb` 및 `outputb` 내에서 명시적으로 진행되는 초기화는 취소됩니다.  
  
 이와 같은 방식으로 언어 개발자에게 필요한 융통성은 확보할 수 있지만 의미가 복잡해지는 대가를 치러야 했습니다.  가상 기본 클래스는 상태 비저장 클래스로 제한하고 여기서 인터페이스를 지정할 수 있도록만 허용하면 컴파일에 따른 부담을 덜 수 있습니다.  C\+\+에서 권장하는 디자인 방식은 바로 이와 같습니다.  CLR 프로그래밍의 경우 이는 인터페이스 형식과 관련된 정책 문제로 발전합니다.  
  
 다음은 간단한 코드 예제입니다. 여기에서는 명시적 boxing이 필요하지 않습니다.  
  
```  
// Managed Extensions for C++ requires explicit __box operation  
int my1DIntArray __gc[] = { 1, 2, 3, 4, 5 };  
Object* myObjArray __gc[] = {   
   __box(26), __box(27), __box(28), __box(29), __box(30)  
};  
  
Console::WriteLine( "{0}\t{1}\t{2}", __box(0),  
   __box(my1DIntArray->GetLowerBound(0)),  
   __box(my1DIntArray->GetUpperBound(0)) );  
```  
  
 예제에서 볼 수 있듯이 매우 많은 boxing이 진행됩니다.  [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서 값 형식 boxing은 암시적입니다.  
  
```  
// new syntax makes boxing implicit  
array<int>^ my1DIntArray = {1,2,3,4,5};  
array<Object^>^ myObjArray = {26,27,28,29,30};  
  
Console::WriteLine( "{0}\t{1}\t{2}", 0,   
   my1DIntArray->GetLowerBound( 0 ),   
   my1DIntArray->GetUpperBound( 0 ) );  
```  
  
## 참고 항목  
 [값 형식 및 동작\(C\+\+\/CLI\)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [Boxing](../windows/boxing-cpp-component-extensions.md)