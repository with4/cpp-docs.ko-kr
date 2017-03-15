---
title: "관리되는 클래스 형식 선언 | Microsoft Docs"
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
  - "__gc 형식"
  - "__value 키워드"
  - "class 키워드[C++], CLR"
  - "클래스[C++], 관리"
  - "interface class 키워드"
  - "관리되는 클래스"
  - "ref 키워드[C++]"
  - "value 키워드[C++]"
  - "값 형식, 선언"
ms.assetid: 16de9c94-91d7-492f-8ac7-f0729cc627e9
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# 관리되는 클래스 형식 선언
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서는 참조 클래스 형식을 선언하는 방법이 Managed Extensions for C\+\+와 다르게 변경되었습니다.  
  
 Managed Extensions의 경우에는 참조 클래스 형식 앞에 `__gc` 키워드가 추가됩니다.  새 구문에서는 `__gc` 키워드가 `ref class` 또는 `ref struct`라는 공백이 포함된 두 키워드 중 하나로 대체됩니다.  `struct`와 `class` 중 어느 것을 사용하는지에 따라 형식 본문 맨 앞의 레이블 없는 섹션에서 선언되는 멤버의 기본 액세스 수준이 public인지\(`struct`의 경우\) 또는 private인지\(`class`의 경우\)가 지정됩니다.  
  
 마찬가지로 Managed Extensions의 경우에는 값 클래스 형식 앞에 `__value` 키워드가 추가됩니다.  새 구문에서는 `__value` 키워드가 `value class` 또는 `value struct`라는 공백이 포함된 두 키워드 중 하나로 대체됩니다.  
  
 Managed Extensions의 경우 인터페이스 형식은 `__interface` 키워드를 사용하여 지정합니다.  새 구문에서는 이 키워드가 `interface class`로 대체되었습니다.  
  
 예를 들어, 다음은 Managed Extensions의 클래스 선언입니다.  
  
```  
public __gc class Block {};     // reference class  
public __value class Vector {}; // value class  
public __interface IFooBar {};  // interface class  
```  
  
 새 구문에서는 이를 다음과 같이 선언합니다.  
  
```  
public ref class Block {};         // reference class  
public value class Vector {};      // value class  
public interface class IFooBar {}; // interface class  
```  
  
## 클래스를 abstract로 지정  
 Managed Extensions의 경우 클래스가 완전하지 않으며 프로그램 내에서 클래스의 개체를 만들 수 없음을 나타내기 위해 `class` 키워드 앞에서 `__gc` 앞이나 뒤에 `__abstract` 키워드를 배치했습니다.  
  
```  
public __gc __abstract class Shape {};  
public __gc __abstract class Shape2D: public Shape {};  
```  
  
 새 구문에서는 클래스 이름과 클래스 본문, 기본 클래스 파생 목록 또는 세미콜론 사이에 `abstract` 컨텍스트 키워드를 지정합니다.  
  
```  
public ref class Shape abstract {};  
public ref class Shape2D abstract : public Shape{};  
```  
  
 물론 의미는 달라지지 않았습니다.  
  
## 클래스를 sealed로 지정  
 Managed Extensions의 경우 클래스의 개체가 상속될 수 없음을 나타내기 위해 `class` 키워드 앞에서 `__gc` 앞이나 뒤에 `__sealed` 키워드를 배치했습니다.  
  
```  
public __gc __sealed class String {};  
```  
  
 새 구문에서는 클래스 이름과 클래스 본문, 기본 클래스 파생 목록 또는 세미콜론 사이에 `sealed` 컨텍스트 키워드를 지정합니다.  
  
 클래스를 파생하면서 봉인할 수 있습니다.  예를 들어, `String` 클래스는 `Object`에서 암시적으로 파생됩니다.  클래스를 봉인하면 봉인된 참조 클래스 개체를 통해 모든 가상 함수 호출을 컴파일 타임에 정적으로 해결할 수 있다는 이점이 있습니다.  `sealed` 지정자를 사용하면 호출하려는 가상 메서드의 재정의 인스턴스를 제공할 수 있는 이후의 파생 클래스를 `String` 추적 핸들이 참조할 수 없기 때문입니다.  다음은 새 구문의 봉인 클래스 예제입니다.  
  
```  
public ref class String sealed {};  
```  
  
 추상인 동시에 봉인된 클래스를 지정할 수도 있습니다. 이는 정적 클래스를 나타내는 특별한 조건입니다.  여기에 대해서는 다음과 같은 CLR 문서의 내용을 참조하십시오.  
  
 "`abstract`인 동시에 `sealed`인 형식은 정적 멤버만 가져야 하고 일부 언어에서 네임스페이스라고 칭하는 역할을 수행합니다."  
  
 예를 들어, Managed Extensions 구문에서는 다음과 같은 추상 봉인 클래스의 선언을 사용합니다.  
  
```  
public __gc __sealed __abstract class State {  
public:  
   static State() {}  
   static bool inParamList();  
  
private:  
   static bool ms_inParam;  
};  
```  
  
 새 구문에서는 위 선언이 다음과 같이 변환됩니다.  
  
```  
public ref class State abstract sealed {  
public:  
   static State();  
   static bool inParamList();  
  
private:  
   static bool ms_inParam;  
};  
```  
  
## CLR 상속: 기본 클래스 지정  
 CLR 개체 모델에서는 공용 단일 상속만 지원됩니다.  그러나 Managed Extensions는 전용 파생을 지정하여 액세스 키워드 없이도 기본 클래스에 대한 ISO\-C\+\+ 기본 해석을 유지합니다.  즉, CLR 상속 선언마다 `public` 키워드를 제공하여 기본 해석을 재정의해야 합니다.  
  
```  
// Managed Extensions: error: defaults to private derivation  
__gc class Derived : Base {};  
```  
  
 새 구문 정의에서는 CLR 상속 정의에 액세스 키워드가 없으면 public 파생이 지정됩니다.  따라서 `public` 액세스 키워드는 이제 선택적 요소입니다.  이와 관련하여 Managed Extensions for C\+\+ 코드를 수정할 필요는 없지만 필요한 경우 아래의 변경 내용을 참조하십시오.  
  
```  
// New syntax: ok: defaults to public derivation  
ref class Derived : Base{};  
```  
  
## 참고 항목  
 [관리되는 형식\(C\+\+\/CL\)](../dotnet/managed-types-cpp-cl.md)   
 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)   
 [abstract](../windows/abstract-cpp-component-extensions.md)   
 [sealed](../windows/sealed-cpp-component-extensions.md)