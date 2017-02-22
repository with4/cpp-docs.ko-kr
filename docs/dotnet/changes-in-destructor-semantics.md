---
title: "소멸자 의미의 변경 내용 | Microsoft Docs"
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
  - "소멸자, C++"
  - "종료자[C++]"
ms.assetid: f1869944-a407-452f-b99a-04d8c209f0dc
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# 소멸자 의미의 변경 내용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서는 클래스 소멸자 의미가 Managed Extensions for C\+\+와 상당히 다르게 변경되었습니다.  
  
 Managed Extensions에서는 참조 클래스 내에서 클래스 소멸자를 사용할 수 있었지만 값 클래스 내에서는 사용할 수 없었습니다.  이는 새 구문에서도 달라지지 않았습니다.  그러나 클래스 소멸자 의미에는 변경된 점이 있습니다.  이 항목에서는 이러한 변경이 이루어진 이유를 중심으로 기존 CLR 코드 변환에 미치는 영향에 대해 설명합니다.  이 내용은 두 언어 버전 사이에서 프로그래머 수준의 변경 내용 중 가장 중요한 사항입니다.  
  
## 명확하지 않은 종료  
 가비지 수집기에서 개체에 연결된 메모리를 회수하기 전에 관련된 `Finalize` 메서드가 있으면 이 메서드가 호출됩니다.  이 메서드는 개체의 프로그램 수명을 따르지 않으므로 이 메서드를 일종의 상위 소멸자라고 할 수 있습니다.  이를 종료라고 합니다.  `Finalize` 메서드가 호출되는 정확한 시점 또는 호출되는지 여부는 정의되지 않습니다.  가비지 수집에서 명확하지 않은 종료를 수행한다는 것은 이러한 의미입니다.  
  
 명확하지 않은 종료는 동적 메모리 관리에서 잘 작동합니다.  사용 가능한 메모리가 부족해지면 가비지 수집이 작동합니다.  가비지 수집 환경에서는 메모리를 확보하기 위한 소멸자가 필요하지 않습니다.  그러나 개체에서 데이터베이스 연결이나 특정 유형의 잠금과 같은 중요한 리소스를 유지하는 경우에는 명확하지 않은 종료가 제대로 작동하지 않습니다.  이러한 경우 해당 리소스를 최대한 빨리 해제해야 합니다.  네이티브 코드 환경에서는 생성자\/소멸자 쌍을 사용하여 이 작업을 수행했습니다.  개체가 선언된 로컬 블록이 끝나거나 예외가 throw되어 스택이 해제되어 개체의 수명이 끝나면 소멸자가 즉시 실행되어 리소스가 자동으로 해제됩니다.  이 방식은 매우 잘 작동하지만, Managed Extensions에서는 이 방식이 배제되었습니다.  
  
 CLR이 제공하는 해결책은 클래스에서 `IDisposable` 인터페이스의 `Dispose` 메서드를 구현하는 것입니다.  이 방식의 문제점은 사용자가 명시적으로 `Dispose`를 호출해야 한다는 것입니다.  이 과정에서 실수가 발생하기 쉽습니다.  C\# 언어에서는 특수한 `using` 문을 통해 어느 정도의 자동화를 제공합니다.  Managed Extensions 디자인에서는 이와 관련된 특수 기능이 지원되지 않았습니다.  
  
## Managed Extensions for C\+\+의 소멸자  
 Managed Extensions에서 참조 클래스의 소멸자는 다음과 같은 두 단계를 통해 구현됩니다.  
  
1.  사용자가 제공한 소멸자의 이름이 내부적으로 `Finalize`로 변경됩니다.  CLR 개체 모델에서는 단일 상속만 지원되며, 클래스에 기본 클래스가 있는 경우 컴파일러는 사용자가 제공한 코드가 실행되는 부분 뒤에 해당 종료자에 대한 호출을 추가합니다.  예를 들어 Managed Extensions 언어 사양에 있는 다음과 같은 간단한 계층 구조를 살펴 봅니다.  
  
```  
__gc class A {  
public:  
   ~A() { Console::WriteLine(S"in ~A"); }  
};  
  
__gc class B : public A {  
public:  
   ~B() { Console::WriteLine(S"in ~B");  }  
};  
```  
  
 이 예제에서는 두 소멸자의 이름이 모두 `Finalize`로 바뀝니다.  `B`의 `Finalize`에는 `WriteLine` 호출 뒤에 `A`의 `Finalize` 메서드에 대한 호출이 추가됩니다.  가비지 수집기는 종료 도중 기본적으로 이 메서드를 호출합니다.  위 코드는 내부적으로 다음과 같이 변환됩니다.  
  
```  
// internal transformation of destructor under Managed Extensions  
__gc class A {  
public:  
   void Finalize() { Console::WriteLine(S"in ~A"); }  
};  
  
__gc class B : public A {  
public:  
   void Finalize() {   
      Console::WriteLine(S"in ~B");  
      A::Finalize();   
   }  
};  
```  
  
1.  두 번째 단계에서 컴파일러는 가상 소멸자를 합성합니다.  Managed Extensions 사용자 프로그램에서는 이 소멸자를 직접 호출하거나 delete 문을 활용하여 호출합니다.  가비지 수집기에서는 이 소멸자를 호출하지 않습니다.  
  
     이 합성된 소멸자에 명령문 두 개가 배치됩니다.  첫 번째 문에서는 `Finalize`가 더 이상 호출되지 않도록 `GC::SuppressFinalize`를 호출합니다.  두 번째 문에서는 해당 클래스에 사용자가 제공한 소멸자를 나타내는 `Finalize`를 실제로 호출합니다.  합성된 소멸자는 다음과 같습니다.  
  
```  
__gc class A {  
public:  
   virtual ~A() {  
      System::GC::SuppressFinalize(this);  
      A::Finalize();  
   }  
};  
  
__gc class B : public A {  
public:  
   virtual ~B() {  
      System::GC::SuppressFinalize(this);  
      B::Finalize();  
   }  
};  
```  
  
 이러한 구현 방식에서는 사용자가 전혀 제어할 수 없었던 이전에 비해 사용자가 클래스의 `Finalize` 메서드를 직접 호출할 수 있다는 점이 다르지만, `Dispose` 메서드에 의한 해결 방법과 실제로 연계되는 것은 아닙니다.  이는 [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서 변경되었습니다.  
  
## 새 구문의 소멸자  
 새 구문에서는 소멸자의 이름이 내부적으로 `Dispose` 메서드로 변경되고 참조 클래스가 `IDispose` 인터페이스를 구현하도록 자동으로 확장됩니다.  즉, 이전에 살펴본 클래스 쌍은 [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서 다음과 같이 변환됩니다.  
  
```  
// internal transformation of destructor under the new syntax  
__gc class A : IDisposable {  
public:  
   void Dispose() {   
      System::GC::SuppressFinalize(this);  
      Console::WriteLine( "in ~A");  
   }  
};  
  
__gc class B : public A {  
public:  
   void Dispose() {   
      System::GC::SuppressFinalize(this);  
      Console::WriteLine( "in ~B");    
      A::Dispose();   
   }  
};  
```  
  
 새 구문에서는 소멸자가 명시적으로 호출되거나 추적 핸들에 `delete`가 적용되면 내부 `Dispose` 메서드가 자동으로 호출됩니다.  파생 클래스의 경우 합성된 메서드의 마지막에 기본 클래스의 `Dispose` 메서드에 대한 호출이 삽입됩니다.  
  
 그러나 아직 명확한 종료를 수행할 수 있는 것은 아닙니다.  이를 위해서는 로컬 참조 개체를 추가로 사용해야 합니다. Managed Extensions에는 여기에 해당하는 지원이 없으므로 이는 변환에 관련된 문제는 아닙니다.  
  
## 참조 개체 선언  
 [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서는 참조 클래스의 개체를 직접 액세스할 수 있는 것처럼 로컬 스택에 선언하거나 클래스 멤버로 선언할 수 있습니다.  이 기능이 소멸자와 `Dispose` 메서드를 연결하는 기능과 결합되면 참조 형식에 대한 종료 구문 호출을 자동화할 수 있습니다.  
  
 우선 개체를 만들면 클래스 생성자를 통해 리소스를 얻는 참조 클래스를 정의합니다.  그런 다음 클래스 소멸자 내에서 개체가 만들어질 때 얻은 리소스를 해제합니다.  
  
```  
public ref class R {  
public:  
   R() { /* acquire expensive resource */ }  
   ~R() { /* release expensive resource */ }  
  
   // … everything else …  
};  
```  
  
 형식 이름을 사용하여 개체를 로컬로 선언했지만 캐럿은 사용되지 않았습니다.  메서드를 호출할 때와 같이 개체를 사용할 때는 화살표\(`->`\) 대신 멤버 선택 점\(`.`\)을 사용합니다.  다음과 같이 블록 끝에서 `Dispose`로 변환된 관련 소멸자가 자동으로 호출됩니다.  
  
```  
void f() {  
   R r;   
   r.methodCall();  
  
   // r is automatically destructed here –  
   // that is, r.Dispose() is invoked  
}  
```  
  
 C\# 내의 `using` 문과 마찬가지로 이 기능은 모든 참조 형식이 CLR 힙에 할당되어야 한다는 내부 CLR 제약 조건을 준수하고 있습니다.  내부적인 의미는 변경되지 않습니다.  사용자는 컴파일러에서 수행하는 내부 변환과 유사한 다음과 같은 동등한 코드를 작성할 수도 있습니다.  
  
```  
// equivalent implementation  
// except that it should be in a try/finally clause  
void f() {  
   R^ r = gcnew R;   
   r->methodCall();  
  
   delete r;  
}  
```  
  
 새 구문에서는 실제로 소멸자와 생성자가 다시 짝을 이루어 로컬 개체의 수명에 자동화된 획득\/해제 메커니즘으로 연결됩니다.  
  
## 명시적 종료 선언  
 앞서 설명한 것처럼 새 구문에서는 소멸자가 `Dispose` 메서드로 합성됩니다.  따라서 소멸자가 명시적으로 호출되지 않는 경우 종료 도중 가비지 수집기에서는 예전처럼 개체의 관련 `Finalize` 메서드를 찾지 못합니다.  소멸과 종료를 모두 지원하기 위해 종료자를 제공하는 특수한 구문이 도입되었습니다.  예를 들면 다음과 같습니다.  
  
```  
public ref class R {  
public:  
   !R() { Console::WriteLine( "I am the R::finalizer()!" ); }  
};  
```  
  
 `!` 접두사는 클래스 소멸자를 나타내는 물결표\(`~`\)와 비슷합니다. 즉, 두 가지 수명 후 메서드에는 모두 클래스 이름 앞에 토큰이 추가됩니다.  합성된 `Finalize` 메서드가 파생 클래스 내에서 호출되면 마지막에 기본 클래스의 `Finalize` 메서드 호출이 삽입됩니다.  소멸자가 명시적으로 호출되면 종료자는 호출되지 않습니다.  변환 결과는 다음과 같습니다.  
  
```  
// internal transformation under new syntax  
public ref class R {  
public:  
   void Finalize() {  
      Console::WriteLine( "I am the R::finalizer()!" );  
   }  
};   
```  
  
## Managed Extensions for C\+\+에서 Visual C\+\+ 2005로 전환  
 Managed Extensions for C\+\+ 프로그램을 [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서 컴파일하면 참조 클래스에 내용이 있는 소멸자가 있는 경우 런타임 동작이 변경됩니다.  따라서 다음과 같은 알고리즘에 따라 코드를 변환해야 합니다.  
  
1.  소멸자가 있는 경우 클래스 종료자가 되도록 다시 작성합니다.  
  
2.  `Dispose` 메서드가 있는 경우 클래스 소멸자로 다시 작성합니다.  
  
3.  소멸자는 있지만 `Dispose` 메서드가 없는 경우 첫 번째 항목을 수행하면서 소멸자를 유지합니다.  
  
 코드를 Managed Extensions에서 새 구문으로 전환할 때 실수로 이러한 변환을 수행하지 않을 수 있습니다.  응용 프로그램이 관련된 종료 메서드의 실행에 의존하는 경우 응용 프로그램의 동작이 내부적으로 프로그래머의 의도와 달라지게 됩니다.  
  
## 참고 항목  
 [관리되는 형식\(C\+\+\/CL\)](../dotnet/managed-types-cpp-cl.md)   
 [Visual C\+\+의 소멸자 및 종료자](../misc/destructors-and-finalizers-in-visual-cpp.md)