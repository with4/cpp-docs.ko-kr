---
title: "대리자 및 이벤트 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__delegate 키워드"
  - "__event 키워드[C++]"
  - "delegate 키워드[C++]"
  - "대리자[C++], Managed Extensions for C++에서 업그레이드"
  - "event 키워드[C++]"
  - "이벤트[C++], Managed Extensions for C++에서 업그레이드"
ms.assetid: 3505c626-7e5f-4492-a947-0e2248f7b84a
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 대리자 및 이벤트
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서는 대리자와 이벤트를 선언하는 방법이 Managed Extensions for C\+\+와 다르게 변경되었습니다.  
  
 다음 샘플에서 볼 수 있듯이 두 개의 밑줄은 더 이상 필요하지 않습니다.  다음은 Managed Extensions의 샘플 코드입니다.  
  
```  
__delegate void ClickEventHandler(int, double);  
__delegate void DblClickEventHandler(String*);  
  
__gc class EventSource {  
   __event ClickEventHandler* OnClick;    
   __event DblClickEventHandler* OnDblClick;    
};  
```  
  
 새 구문에서는 같은 코드가 다음과 같이 사용됩니다.  
  
```  
delegate void ClickEventHandler( int, double );  
delegate void DblClickEventHandler( String^ );  
  
ref class EventSource {  
   event ClickEventHandler^ OnClick;   
   event DblClickEventHandler^ OnDblClick;   
};  
```  
  
 이벤트와 대리자는 참조 형식이며, 새 구문에서는 캐럿\(`^`\)이 사용되어 이를 분명히 알 수 있습니다.  이벤트의 경우에는 명시적 선언 구문과 위 코드의 간편한 형식이 모두 지원됩니다.  명시적 형식에서 사용자는 이벤트와 관련된 `add`, `raise` 및 `remove` 메서드를 지정합니다. `add` 및 `remove` 메서드만 필수 요소이고 `raise` 메서드는 선택 요소입니다.  
  
 Managed Extensions에서는 이러한 메서드를 제공하는 경우 명시적 이벤트 선언을 함께 제공하지 않지만, 존재하지 않는 이벤트의 이름을 결정해야 합니다.  Managed Extensions 사양에서 발췌한 다음 예제와 같이 각 메서드는 `add_EventName`, `raise_EventName` 및 `remove_EventName` 형식으로 지정됩니다.  
  
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
  
 아래의 변환된 코드에서 알 수 있듯이 새 구문에서는 선언이 간소화됩니다.  이벤트는 다음과 같이 이벤트 및 관련 대리자 형식 선언 바로 뒤에서 중괄호로 묶인 두 세 개의 메서드를 지정할 수 있습니다.  
  
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
  
## 참고 항목  
 [클래스 또는 인터페이스 내에서 멤버 선언\(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [delegate](../windows/delegate-cpp-component-extensions.md)   
 [event](../windows/event-cpp-component-extensions.md)