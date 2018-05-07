---
title: 참조 형식에 대 한 c + + 스택 의미 체계 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- reference types, C++ stack semantics for
ms.assetid: 319a1304-f4a4-4079-8b84-01cec847d531
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b3ed886d1bdeb4972122049854b5d288767aa5b8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="c-stack-semantics-for-reference-types"></a>참조 형식에 대한 C++ 스택 의미 체계
Visual c + + 2005 이전 참조 형식의 인스턴스만 만들 수를 사용 하는 `new` 수집 되는 힙에 가비지에 개체를 생성 하는 연산자입니다. 그러나 스택에 네이티브 형식의 인스턴스를 만드는 데 사용할 수 있는 동일한 구문을 사용 하는 참조 형식의 인스턴스를 지금 만들 수 있습니다. 사용할 필요가 없습니다 따라서 [ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md) 참조 형식의 개체를 만듭니다. 및이 개체가 범위를 벗어나면 컴파일러가 개체의 소멸자가 호출 합니다.  
  
## <a name="remarks"></a>설명  
 컴파일러 내부적으로 가비지 수집 된 힙에 인스턴스를 만듭니까 스택 의미 체계를 사용 하 여 참조 형식의 인스턴스를 만들 때 (사용 하 여 `gcnew`).  
  
 함수 시그니처 또는 반환 형식 값에 의해 참조 형식의 인스턴스를 포함 하는 경우에 함수 (modreq)와 특수 처리를 필요로 하는 컨트롤로 메타 데이터에 표시 됩니다. 이 특수 처리는 현재 Visual c + + 클라이언트;에서 제공 스택 의미 체계를 사용 하 여 만든 참조 형식을 사용 하는 데이터 또는 함수를 사용 중인 다른 언어는 현재 지원 하지 않습니다.  
  
 사용 하는 한 가지 이유 `gcnew` (동적 할당) 스택 대신 의미 형식에 소멸자가 되지 않은 경우 될 것입니다. 또한 참조 형식 함수 서명이 스택 의미 체계를 사용 하 여 만든를 사용 하 여 가능 하지 않습니다 함수 Visual c + + 이외의 언어에서 사용할 수 있도록 하려는 경우.  
  
 컴파일러는 참조 형식에 대 한 복사 생성자를 생성 하지 않습니다. 따라서 값에 의해 참조 형식 서명에 사용 하는 함수를 정의 하는 경우 참조 형식에 대 한 복사 생성자를 정의 해야 합니다. 참조 형식에 대 한 복사 생성자에 다음과 같은 형식의 서명이: `R(R%){}`합니다.  
  
 컴파일러는 참조 형식에 대 한 기본 할당 연산자를 생성 하지 않습니다. 할당 연산자를 사용 하면 스택 의미 체계를 사용 하 여 만든 기존 개체를 사용 하 여 초기화 및 스택 의미 체계를 사용 하 여 개체를 만들 수 있습니다. 참조 형식에 대 한 할당 연산자는 다음과 같은 형식의 서명이: `void operator=( R% ){}`합니다.  
  
 해당 형식의 소멸자 중요 한 리소스를 해제 하는 경우 스택 의미 체계를 사용 하 여 참조 형식에 대 한 필요가 없습니다 소멸자를 명시적으로 호출 (호출 또는 `delete`). 참조 형식에서 소멸자에 대 한 자세한 내용은 참조 하십시오. [소멸자 및 종료자에서 하는 방법: 클래스 및 구조체 정의 및 사용 (C + + /cli CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)합니다.  
  
 컴파일러에서 생성 된 할당 연산자는 다음 항목이 추가 된 일반적인 표준 c + + 규칙을 따릅니다.  
  
-   모든 비정적 데이터 멤버는 참조 형식에 대 한 핸들 형식의 됩니다 shallow 복사 된 (형식이 포인터는 비정적 데이터 멤버 처럼 처리 됨).  
  
-   값 형식을 단순 됩니다는 형식의 모든 비정적 데이터 멤버에 복사 합니다.  
  
-   참조 형식이 복사 생성자에 대 한 호출 되는 참조 형식의 인스턴스는 형식의 모든 비정적 데이터 멤버를 호출 합니다.  
  
 컴파일러가 제공는 `%` 내부 핸들 형식으로 스택 의미 체계를 사용 하 여 만든 참조 형식의 인스턴스를 변환 하는 단항 연산자입니다.  
  
 다음 참조 유형 스택 의미 체계에 사용 하기 위해 사용할 수 없습니다.  
  
-   [delegate(C++ 구성 요소 확장)](../windows/delegate-cpp-component-extensions.md)  
  
-   [배열](../windows/arrays-cpp-component-extensions.md)  
  
-   <xref:System.String>  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 코드 샘플에서는 스택 의미 체계를 사용 하 여 참조 형식의 인스턴스를 선언 하는 방법을 보여 줍니다. 방법을 할당 연산자 및 복사 생성자 작동 및 스택 의미 체계를 사용 하 여 만든 참조 형식이 있는 추적 참조를 초기화 하는 방법입니다.  
  
### <a name="code"></a>코드  
  
```  
// stack_semantics_for_reference_types.cpp  
// compile with: /clr  
ref class R {  
public:  
   int i;  
   R(){}  
  
   // assignment operator  
   void operator=(R% r) {  
      i = r.i;  
   }  
  
   // copy constructor  
   R(R% r) : i(r.i) {}  
};  
  
void Test(R r) {}   // requires copy constructor  
  
int main() {  
   R r1;  
   r1.i = 98;  
  
   R r2(r1);   // requires copy constructor  
   System::Console::WriteLine(r1.i);  
   System::Console::WriteLine(r2.i);  
  
   // use % unary operator to convert instance using stack semantics  
   // to its underlying handle  
   R ^ r3 = %r1;  
   System::Console::WriteLine(r3->i);  
  
   Test(r1);  
  
   R r4;  
   R r5;  
   r5.i = 13;  
   r4 = r5;   // requires a user-defined assignment operator  
   System::Console::WriteLine(r4.i);  
  
   // initialize tracking reference  
   R % r6 = r4;  
   System::Console::WriteLine(r6.i);  
}  
```  
  
### <a name="output"></a>출력  
  
```  
98  
98  
98  
13  
13  
```  
  
## <a name="see-also"></a>참고 항목  
 [클래스 및 구조체](../windows/classes-and-structs-cpp-component-extensions.md)