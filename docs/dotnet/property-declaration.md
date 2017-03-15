---
title: "속성 선언 | Microsoft Docs"
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
  - "__property 키워드"
  - "속성 선언, C++"
  - "property 키워드[C++]"
ms.assetid: de169378-a8b8-49f4-a586-76bffc9b5c9f
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 속성 선언
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서는 관리되는 클래스의 속성을 선언하는 방법이 Managed Extensions for C\+\+와 다르게 변경되었습니다.  
  
 Managed Extensions 디자인에서는 각 `set` 또는 `get` 속성 접근자가 독립 메서드로 지정됩니다.  각 메서드 선언에는 `__property` 키워드가 접두사로 붙습니다.  메서드 이름은 `set_` 또는 `get_`으로 시작하며 뒤에 속성의 실제 이름\(사용자에게 표시되는 이름\)이 나옵니다.  따라서 `x` 좌표에 대한 `get` 속성을 제공하는 `Vector`에서는 메서드 이름을 `get_x`로 지정하고 사용자는 `x`를 사용하여 호출합니다.  이러한 명명 규칙 및 메서드 별도 지정은 실제로 속성의 내부 런타임 구현을 반영합니다.  예를 들어 좌표 속성 집합이 있는 `Vector`를 살펴 봅니다.  
  
```  
public __gc __sealed class Vector {  
public:  
   __property double get_x(){ return _x; }  
   __property double get_y(){ return _y; }  
   __property double get_z(){ return _z; }  
  
   __property void set_x( double newx ){ _x = newx; }  
   __property void set_y( double newy ){ _y = newy; }  
   __property void set_z( double newz ){ _z = newz; }  
};  
```  
  
 이렇게 하면 속성에 연결된 기능이 지나치게 노출되고, 사용자가 관련 set 및 get을 구문적으로 통합해야 하며  코딩이 번거롭습니다.  C\#과 유사점이 많은 새 구문에서는 `property` 키워드 뒤에 속성 형식 및 원래대로의 이름이 나옵니다.  `set` 및 `get` 액세스 메서드는 속성 이름 뒤에 나오는 블록 내에 배치됩니다.  C\#과는 달리 액세스 메서드의 시그니처가 지정됩니다.  예를 들어 위 코드 예제를 새 구문으로 변환하면 다음과 같습니다.  
  
```  
public ref class Vector sealed {   
public:  
   property double x {  
      double get() {  
         return _x;  
      }  
  
      void set( double newx ) {  
         _x = newx;  
      }  
   } // Note: no semi-colon  
};  
```  
  
 속성의 액세스 메서드에서 `public` `get` 및 `private` 또는 `protected` `set`과 같은 별도의 액세스 수준을 반영하는 경우 명시적 액세스 레이블을 지정할 수 있습니다.  기본적으로 속성의 액세스 수준은 포함하는 액세스 수준을 반영합니다.  예를 들어 위의 `Vector` 정의에서 `get`과 `set` 메서드는 모두 `public`입니다.  `set` 메서드를 `protected` 또는 `private`로 설정하려면 정의를 다음과 같이 수정합니다.  
  
```  
public ref class Vector sealed {   
public:  
   property double x {  
      double get() {  
         return _x;  
      }  
  
   private:  
      void set( double newx ) {  
         _x = newx;  
      }  
  
   } // note: extent of private culminates here …  
  
// note: dot is a public method of Vector  
double dot( const Vector^ wv );  
  
// etc.  
};  
```  
  
 속성 내에서 액세스 키워드의 범위는 속성의 닫는 중괄호까지 또는 추가 액세스 키워드가 지정될 때까지 연장됩니다.  이 범위는 속성 정의를 넘어 속성 정의가 포함되는 액세스 수준까지 연장되지 않습니다.  예를 들어 위 선언에서 `Vector::dot()`는 public 메서드입니다.  
  
 세 개의 `Vector` 좌표에 대한 set\/get 속성을 작성하려면 다음 세 단계를 거쳐야 합니다.  
  
1.  전용 상태 멤버를 적절한 형식으로 선언합니다.  
  
2.  사용자가 해당 값을 가져오려고 할 때 이 멤버를 반환합니다.  
  
3.  멤버에 새 값을 할당합니다.  
  
 새 구문에서는 이러한 사용 패턴을 자동화하는 약식 속성 구문을 사용할 수 있습니다.  
  
```  
public ref class Vector sealed {   
public:  
   // equivalent shorthand property syntax  
   property double x;   
   property double y;  
   property double z;  
};  
```  
  
 약식 속성 구문을 사용하면 컴파일러에서 내부 상태 멤버가 자동으로 생성되지만 set\/get 접근자를 통해서가 아니면 클래스 내에서 액세스할 수 없다는 흥미로운 부작용이 있습니다.  
  
## 참고 항목  
 [클래스 또는 인터페이스 내에서 멤버 선언\(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [property](../windows/property-cpp-component-extensions.md)