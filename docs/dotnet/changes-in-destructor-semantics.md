---
title: 소멸자 의미의 변경 내용을 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- finalizers [C++]
- destructors, C++
ms.assetid: f1869944-a407-452f-b99a-04d8c209f0dc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8a3d078300ca0e51ba8eb035d5428d300b0413a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="changes-in-destructor-semantics"></a>소멸자 의미의 변경 내용
클래스 소멸자에 대 한 의미는 Visual c + +는 데 Managed Extensions for c + + 크게 변경 되었습니다.  
  
 Managed Extensions 클래스 소멸자는 참조 클래스 내에 있지만 값 클래스 내에 있지 수 있었습니다. 새 구문에서 변경 되지 않았습니다. 그러나 클래스 소멸자의 의미 체계가 변경 되었습니다. 이 항목에 중점을 둡니다 이루어진 이유를 변경 하 고 기존 CLR 코드의 변환에 미치는 영향을 설명 합니다. 언어의 두 버전 간의 가장 중요 한 프로그래머 수준의 변경 때문일 수 있습니다.  
  
## <a name="non-deterministic-finalization"></a>명확 하지 않은 종료  
 연결된 된 가비지 수집기가 개체에 연결 된 메모리를 회수 하기 전에 `Finalize` 메서드가 있는 경우 호출 됩니다. 개체의 프로그램 수명에 연결 되지 않은 때문에 상위 소멸자의 한 종류로이 메서드의 간주할 수 있습니다. 이라고이를 종료 합니다. 타이밍 또는 여부는 `Finalize` 메서드 정의 되지 않습니다. 이 가비지 수집 명확 하지 않은 종료를 수행 하는 것이 말할 때는 의미입니다.  
  
 종료 명확 하지 않은 메모리의 동적 관리와 잘 작동합니다. 사용 가능한 메모리 부족 해지면 가비지 수집기를 시작 합니다. 에 대 한 가비지 수집 환경에서는 소멸자가 사용 가능한 메모리는 필요 하지 않습니다. 그러나 명확 하지 않은 종료가 작동 하지 않습니다, 개체가 데이터베이스 연결 또는 일종의 잠금과 같은 중요 한 리소스를 유지 하는 경우. 이 경우 가능한 한 빨리 해당 리소스를 해제 해야 합니다. 네이티브 코드를 생성자/소멸자 쌍을 사용 하 여 이루어집니다. 개체의 수명이 종료 되는 즉시 선언 된 로컬 블록이 종료 될 때 또는 스택 예외를 발생 시키는 끝나거나 때 소멸자가 실행 하 고 리소스가 자동으로 해제 됩니다. Managed extensions 해당 아키텍처가 없는 경우 빠져 되었습니다 및이 방법은 매우를 잘 작동 합니다.  
  
 CLR에서 제공 되는 솔루션을 구현 하는 클래스에 대 한는 `Dispose` 의 메서드는 `IDisposable` 인터페이스입니다. 이 문제는 `Dispose` 사용자가 명시적 호출 해야 합니다. 이 오류가 발생 하기 쉬운입니다. C# 언어의 특수 한 형태의 자동화 기능을 어느 정도의 제공 `using` 문. Managed Extensions 디자인 없는 특별 한 지원을 제공 했습니다.  
  
## <a name="destructors-in-managed-extensions-for-c"></a>Managed Extensions for c + +의 소멸자  
 Managed extensions에서 참조 클래스의 소멸자는 다음 두 단계를 사용 하 여 구현 됩니다.  
  
1.  사용자가 제공한 소멸자의 이름이 내부적으로 `Finalize`합니다. 클래스에 있는 경우 기본 클래스 (기억, CLR 개체 모델에서는 단일 상속만 지원 됩니다), 컴파일러는 사용자 제공 코드의 실행 뒤에 종료자에 대 한 호출을 추가 합니다. 예를 들어 관리 되는 확장 언어 사양에서 가져온 다음 간단한 계층:  
  
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
  
 이 예제에서는 두 소멸자 이름이 `Finalize`합니다. `B``Finalize` 의 호출에 `A`의 `Finalize` 의 호출 뒤에 추가 메서드가 `WriteLine`합니다. 이 어떤 가비지 수집기는 기본적으로 호출 종료 중입니다. 이 내부 변환의 모양을 다음과 같습니다.  
  
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
  
1.  두 번째 단계에서 컴파일러는 가상 소멸자를 합성 합니다. 이 소멸자는 Managed Extensions 사용자 프로그램 직접적으로 또는 delete 식의 응용 프로그램을 통해 호출 합니다. 가비지 수집기에 의해 호출 되지 않습니다.  
  
     두 개의 문이이 합성 된 소멸자에 배치 됩니다. 하나는에 대 한 호출 `GC::SuppressFinalize` 더 이상 없는 호출 된다고 되도록 `Finalize`합니다. 두 번째는 실제로 호출 `Finalize`, 해당 클래스에 대 한 사용자가 제공한 소멸자를 나타냅니다. 이 모양을 다음과 같습니다.  
  
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
  
 이 구현 클래스를 명시적으로 호출 하는 사용자를 허용 하지만 `Finalize` 메서드 대신, 제어 권한이 없을 한 번에 것 않습니다 하지 실제로 연결할로 `Dispose` 메서드 솔루션입니다. 이 Visual c + +에서 변경 됩니다.  
  
## <a name="destructors-in-new-syntax"></a>새 구문에서 소멸자  
 새 구문에서 소멸자의 이름이 내부적으로 `Dispose` 메서드와 참조 클래스 구현 하도록 자동으로 확장 됩니다는 `IDispose` 인터페이스입니다. 즉, Visual c + +, 클래스 우리의 쌍 변환 되는 다음과 같습니다.  
  
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
  
 새 구문 중 하나는 소멸자를 명시적으로 호출 하거나 `delete` 내부 추적 핸들을 적용 `Dispose` 메서드가 자동으로 호출 됩니다. 파생된 클래스에서 호출의 경우는 `Dispose` 메서드는 기본 클래스의 합성 된 메서드의에 삽입 됩니다.  
  
 그러나이 하지 움직인를 명확한 종료 합니다. 이 위해서는 로컬 참조 개체의 추가 지원이 필요 합니다. (이것은 Managed Extensions 내에서 유사한 지원 하지 않습니다 및 따라서 이것은 변환 문제)  
  
## <a name="declaring-a-reference-object"></a>참조 방식 개체를 선언합니다.  
 Visual c + +에서는 참조 클래스의 개체의 선언 로컬 스택에 클래스의 멤버로 처럼 하거나 직접 액세스할 수 있었습니다. 가진 소멸자의 연결을 함께 사용 하면는 `Dispose` 메서드, 결과 참조 형식에 종료 구문의 자동된 호출 합니다.  
  
 첫째, 개체를 만드는 클래스 생성자를 통해 리소스를 확보도 작동 되도록 참조 클래스를 정의 합니다. 둘째, 클래스 소멸자 내에서 개체를 만들 때 얻은 리소스를 해제 했습니다.  
  
```  
public ref class R {  
public:  
   R() { /* acquire expensive resource */ }  
   ~R() { /* release expensive resource */ }  
  
   // everything else...  
};  
```  
  
 개체 유형 이름을 사용 하 여 로컬로 하지만 괄호 선언 됩니다. 메서드를 호출 하는 등의 개체 사용 되는 모든 멤버 선택 점 통해 수행 됩니다 (`.`) 대신 화살표 (`->`). 블록의 끝에 연결 된 소멸자로 변환 `Dispose`, 다음과 같이 자동으로 호출 됩니다.  
  
```  
void f() {  
   R r;   
   r.methodCall();  
  
   // r is automatically destructed here -  
   // that is, r.Dispose() is invoked  
}  
```  
  
 과 마찬가지로 `using` 문 내에서 C#,이 준수 모든 참조 형식이 기본 CLR 제약 조건을 CLR 힙으로부터에 할당 해야 합니다. 기본 의미 체계가 변경 되지 않습니다. 사용자와 동일한 쓰여 다음 (및이 컴파일러에서 수행 하는 내부 변환과 가능성이):  
  
```  
// equivalent implementation  
// except that it should be in a try/finally clause  
void f() {  
   R^ r = gcnew R;   
   r->methodCall();  
  
   delete r;  
}  
```  
  
 실제로 새 구문에서 소멸자는 다시 이룹니다 생성자는 자동화 된 획득 하 고 해제로 메커니즘 로컬 개체의 수명에 연결 합니다.  
  
## <a name="declaring-an-explicit-finalize"></a>명시적 종료 선언  
 새 구문에서 앞서 설명한 것 처럼 소멸자 합성 됩니다는 `Dispose` 메서드. 즉, 않는 소멸자가 명시적으로 호출 되지 때 가비지 수집기를 종료 하는 동안 이전 처럼 찾지 못합니다 연결 된 `Finalize` 메서드는 개체에 대 한 합니다. 모두 소멸과 종료를 지원 하려면 종료자를 제공 하는 데 특별 한 구문을 도입 되었습니다. 예를 들어:  
  
```  
public ref class R {  
public:  
   !R() { Console::WriteLine( "I am the R::finalizer()!" ); }  
};  
```  
  
 `!` 물결표 접두사 비슷합니다 (`~`) 클래스 소멸자는-즉,와 있는 클래스의 이름 접두사를 추가 하는 토큰입니다. 경우는 합성 된 `Finalize` 메서드 호출을 기본 클래스의 파생된 클래스 내에서 발생 `Finalize` 메서드 끝에 삽입 됩니다. 소멸자가 명시적으로 호출 하면 종료 자가 억제 됩니다. 변환의 모양을 다음과 같습니다.  
  
```  
// internal transformation under new syntax  
public ref class R {  
public:  
   void Finalize() {  
      Console::WriteLine( "I am the R::finalizer()!" );  
   }  
};   
```  
  
## <a name="moving-from-managed-extensions-for-c-to-visual-c-2010"></a>Visual c + + 2010 c + +에 대 한 관리 되는 확장에서 이동  
 참조 클래스에는 특수 소멸자가 포함 된 때마다 Visual c + +에서 컴파일할 때에 Managed Extensions for c + + 프로그램의 런타임 동작 변경 됩니다. 필요한 변환 알고리즘은 다음과 유사 합니다.  
  
1.  소멸자가 있는 경우 클래스 종료 자가 되도록를 다시 작성 합니다.  
  
2.  경우는 `Dispose` 메서드가 있는 클래스 소멸자로 다시 작성 합니다.  
  
3.  소멸자는 않지만 있는 경우 없습니다 `Dispose` 메서드를 첫 번째 항목을 수행 하는 동안 소멸자를 유지 합니다.  
  
 코드를 Managed Extensions를에서 새로운 구문으로 이동에이 변환을 수행 하지 못할 수 있습니다. 응용 프로그램이 어떤 식으로든에서 연관된 종료 메서드의 실행에 종속 하는 경우 응용 프로그램의 동작은 자동으로 의도 한 것과에서 다릅니다.  
  
## <a name="see-also"></a>참고 항목  
 [관리 되는 형식 (C + + /cli CL)](../dotnet/managed-types-cpp-cl.md)   
 [소멸자 및 종료자에서 하는 방법: 클래스 및 구조체 정의 및 사용 (C + + /cli CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)