---
title: "속성 선언 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- __property keyword
- declaring properties, C++
- property keyword [C++]
ms.assetid: de169378-a8b8-49f4-a586-76bffc9b5c9f
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c695bfded782ca4db60618ee556af2b4d2dd69be
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="property-declaration"></a>속성 선언
관리 되는 클래스에서 속성을 선언 하는 방법은 Visual c + + Managed Extensions for c + + 변경 되었습니다.  
  
 Managed extensions에서 각 디자인 `set` 또는 `get` 속성 접근자는 독자적인 방법을로 지정 됩니다. 각 메서드의 선언 접두사로 `__property` 키워드입니다. 메서드 이름으로 시작 하며 `set_` 또는 `get_` 속성 (사용자에 게 표시)으로 실제 이름이 붙습니다. 따라서 한 `Vector` 제공 하는 `x` 조정 `get` 속성 이름을 지정 합니다 `get_x` 사용자로 호출 하 고 `x`합니다. 이 명명 규칙 및 메서드의 별도 사양에는 실제로 속성의 기본 런타임 구현을 반영 합니다. 예를 들어, 다음은 우리의 `Vector` 좌표 속성 집합이 있습니다.  
  
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
  
 이 속성과 관련 된 기능으로 및에서 사용자 관련된 set 및 get 어휘 적으로 통합 해야 합니다. 또한 자세한 정보 표시 됩니다. C# 더 많은 인 새 구문에서는 `property` 키워드 뒤 속성 유형과 그 그대로 이름입니다. `set` 및 `get` 액세스 방법을 속성 이름 뒤에 블록 내에 배치 됩니다. 액세스 방법의 서명을 지정 되어 C#과 달리 있는지 확인 합니다. 예를 들어 다음은 코드 예제 위의 새 구문으로 변환 합니다.  
  
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
  
 속성의 액세스 방법을 같은 별도 액세스 수준-을 반영 하는 경우는 `public get` 및 `private` 또는 `protected set`, 명시적 액세스 레이블을 지정할 수 있습니다. 기본적으로 속성의 액세스 수준을 바깥쪽 액세스 수준을 반영합니다. 예를 들어 위의 정의에서 `Vector`모두는 `get` 및 `set` 메서드는 `public`합니다. 확인 하는 `set` 메서드 `protected` 또는 `private`, 정의 다음과 같이 수정 합니다.  
  
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
  
   } // note: extent of private culminates here  
  
// note: dot is a public method of Vector  
double dot( const Vector^ wv );  
  
// etc.  
};  
```  
  
 액세스 키워드는 속성 내에서 범위는 속성의 닫는 중괄호 추가 액세스 키워드가 지정 될 때까지 확장합니다. 속성이 정의 된 바깥쪽 액세스 수준을 속성의 정의 이상을 확장 되지 않습니다. 예를 들어 위 선언에서 `Vector::dot()` 공용 메서드입니다.  
  
 Set/get 속성 3 개에 대 한 쓰기 `Vector` 좌표 세 단계가 포함 됩니다.  
  
1.  적절 한 형식의 전용 상태 멤버를 선언 합니다.  
  
2.  사용자가 해당 값을 가져올지 하고자 할 때 반환 합니다.  
  
3.  새 값으로 할당 합니다.  
  
 새 구문에서 한 줄임 속성 구문은 사용할 수 있는이 사용 패턴을 자동화 하 다음과 같습니다.  
  
```  
public ref class Vector sealed {   
public:  
   // equivalent shorthand property syntax  
   property double x;   
   property double y;  
   property double z;  
};  
```  
  
 줄임 속성 구문을 흥미로운 부작용은 컴파일러에서 내부 상태 멤버가 생성 하지만 것 하지 set/get 접근자를 통해 제외 하 고 클래스 내에서 액세스할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 또는 인터페이스 내에서 멤버 선언 (C + + /cli CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [속성](../windows/property-cpp-component-extensions.md)