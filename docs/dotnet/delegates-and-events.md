---
title: 대리자 및 이벤트 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __event keyword [C++]
- delegate keyword [C++]
- delegates [C++], upgrading from Managed Extensions for C++
- __delegate keyword
- events [C++], upgrading from Managed Extensions for C++
- event keyword [C++]
ms.assetid: 3505c626-7e5f-4492-a947-0e2248f7b84a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 69e0ffcb9b9c48de152a383b4b9a3f6edbe99f42
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33108333"
---
# <a name="delegates-and-events"></a>대리자 및 이벤트
대리자 및 이벤트를 선언 하는 방법은 Visual c + + Managed Extensions for c + + 변경 되었습니다.  
  
 여기서 이중 밑줄이 더 이상 필요 다음 샘플과 같이 합니다. 여기에서 관리 되는 확장 샘플 코드:  
  
```  
__delegate void ClickEventHandler(int, double);  
__delegate void DblClickEventHandler(String*);  
  
__gc class EventSource {  
   __event ClickEventHandler* OnClick;    
   __event DblClickEventHandler* OnDblClick;    
};  
```  
  
 새 구문에서 동일한 코드의 모양은 다음과 같습니다.  
  
```  
delegate void ClickEventHandler( int, double );  
delegate void DblClickEventHandler( String^ );  
  
ref class EventSource {  
   event ClickEventHandler^ OnClick;   
   event DblClickEventHandler^ OnDblClick;   
};  
```  
  
 이벤트 및 대리자는 참조 형식에는 hat 사용 했기 때문에 새 구문 분명 변수인 (`^`).  이벤트에는 명시적 선언 구문 및 앞 코드 에서처럼 사소한 형식을 모두 지원 합니다. 명시적 형식에서 사용자 지정의 `add`, `raise`, 및 `remove` 이벤트와 연결 된 메서드. (만 `add` 및 `remove` 메서드는; `raise` 메서드는 선택 사항입니다.)  
  
 Managed extensions 이러한 메서드를 제공 하는 경우는 명시적 이벤트 선언도 제공 하지 않지만 존재 하지 않는 이벤트의 이름을 결정 해야 합니다. 폼에 각 방법이 지정 되어 `add_EventName`, `raise_EventName`, 및 `remove_EventName`Managed Extensions 사양에서 가져온 다음 예제와 같이,:  
  
```  
// explicit implementations of add, remove, raise  
public __delegate void f(int);  
public __gc struct E {  
   f* _E;  
public:  
   E() { _E = 0; }  
  
   __event void add_E1(f* d) { _E += d; }  
  
   static void Go() {  
      E* pE = new E;  
      pE->E1 += new f(pE, &E::handler);  
      pE->E1(17);   
      pE->E1 -= new f(pE, &E::handler);  
      pE->E1(17);   
   }  
  
private:  
   __event void raise_E1(int i) {  
      if (_E)  
         _E(i);  
   }  
  
protected:  
   __event void remove_E1(f* d) {  
      _E -= d;  
   }  
};  
```  
  
 새 구문 다음 변환에서 보여 주듯이 선언을 간소화 합니다. 이벤트를 지정 하는 두 또는 세 가지 메서드는 한 쌍의 중괄호 포함 하 고 다음과 같이 이벤트 및 해당 관련된 대리자 형식이 선언 바로 뒤에 배치:  
  
```  
public delegate void f( int );  
public ref struct E {  
private:  
   f^ _E; // delegates are also reference types  
  
public:  
   E() {  // note the replacement of 0 with nullptr!  
      _E = nullptr;   
   }  
  
   // the new aggregate syntax of an explicit event declaration  
   event f^ E1 {  
   public:  
      void add( f^ d ) {  
         _E += d;  
      }  
  
   protected:  
      void remove( f^ d ) {  
         _E -= d;  
      }  
  
   private:  
      void raise( int i ) {  
         if ( _E )  
            _E( i );  
      }  
   }  
  
   static void Go() {  
      E^ pE = gcnew E;  
      pE->E1 += gcnew f( pE, &E::handler );  
      pE->E1( 17 );   
      pE->E1 -= gcnew f( pE, &E::handler );  
      pE->E1( 17 );   
   }  
};  
```  
  
## <a name="see-also"></a>참고 항목  
 [클래스 또는 인터페이스 내에서 멤버 선언 (C + + /cli CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [대리자 (c + + 구성 요소 확장명)](../windows/delegate-cpp-component-extensions.md)   
 [event](../windows/event-cpp-component-extensions.md)