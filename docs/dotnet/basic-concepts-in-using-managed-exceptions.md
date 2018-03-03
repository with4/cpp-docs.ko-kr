---
title: "관리 되는 예외 사용의 기본 개념 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- try-catch exception handling, managed applications
- __finally keyword, managed exceptions
- exceptions, managed
- try-catch exception handling
- catch blocks
- throwing exceptions, managed exceptions
- Visual C++, handling managed exceptions
ms.assetid: 40ce8931-1ecc-491a-815f-733b23fcba35
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5e2faf56f050610e6c98ff82cdca10333a54fd93
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="basic-concepts-in-using-managed-exceptions"></a>관리되는 예외 사용의 기본 개념
이 항목에서는 관리 되는 응용 프로그램에서 예외 처리를 설명 합니다. 즉, 응용 프로그램을 사용 하 여 컴파일한는 **/clr** 컴파일러 옵션입니다.  
  
## <a name="in-this-topic"></a>항목 내용  
  
-   [/Clr에서 예외를 throw합니다.](#vcconbasicconceptsinusingmanagedexceptionsanchor1)  
  
-   [Try/Catch 블록 CLR 확장에 대 한](#vcconbasicconceptsinusingmanagedexceptionsanchor2)  
  
## <a name="remarks"></a>설명  
 사용 하 여 컴파일하면는 **/clr** 옵션을 표준 뿐만 아니라 CLR 예외를 처리할 수 있습니다 [c + + 예외 처리](../cpp/cpp-exception-handling.md) 및 [구조적 예외 처리](../cpp/structured-exception-handling-c-cpp.md) (SEH). CLR 예외는 관리 되는 형식에서 throw 된 모든 예외입니다. [system:: exception](https://msdn.microsoft.com/en-us/library/system.exception.aspx) 클래스 CLR 예외 처리를 위한 많은 유용한 메서드를 제공 하 고 사용자 정의 예외 클래스에 대 한 기본 클래스로 사용 하는 것이 좋습니다.  
  
 인터페이스에서 파생 된 예외 형식을 catch 할에서 지원 되지 않습니다 **/clr**합니다. 또한 공용 언어 런타임 허용 하지 않습니다; 스택 오버플로 예외를 catch 할 수 스택 오버플로 예외는 프로세스가 종료 됩니다.  
  
 관리 되는, 관리 되지 않는 응용 프로그램에서 예외 처리에서 차이점에 대 한 자세한 내용은 참조 [예외 처리 동작에서 Managed Extensions for c + +의에서 차이](../dotnet/differences-in-exception-handling-behavior-under-clr.md)합니다.  
  
##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor1"></a>/Clr에서 예외를 throw합니다.  
 CLR 형식에 대 한 핸들을 throw 하는 c + + throw 식 확장 됩니다. 다음 예제에서는 사용자 지정 예외 유형을 만들고 해당 형식의 인스턴스를 throw 합니다.  
  
```  
// clr_exception_handling.cpp  
// compile with: /clr /c  
ref struct MyStruct: public System::Exception {  
public:  
   int i;  
};  
  
void GlobalFunction() {  
   MyStruct^ pMyStruct = gcnew MyStruct;  
   throw pMyStruct;  
}  
```  
  
 값 형식이 throw 하기 전에 boxed 해야 합니다.  
  
```  
// clr_exception_handling_2.cpp  
// compile with: /clr /c  
value struct MyValueStruct {  
   int i;  
};  
  
void GlobalFunction() {  
   MyValueStruct v = {11};  
   throw (MyValueStruct ^)v;  
}  
```  
  
##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor2"></a>Try/Catch 블록 CLR 확장에 대 한  
 동일한 **시도**/**catch** CLR와 네이티브 예외를 catch 하기 위한 블록 구조를 사용할 수 있습니다.  
  
```  
// clr_exception_handling_3.cpp  
// compile with: /clr  
using namespace System;  
ref struct MyStruct : public Exception {  
public:  
   int i;  
};  
  
struct CMyClass {  
public:  
   double d;  
};  
  
void GlobalFunction() {  
   MyStruct^ pMyStruct = gcnew MyStruct;  
   pMyStruct->i = 11;  
   throw pMyStruct;  
}  
  
void GlobalFunction2() {  
   CMyClass c = {2.0};  
   throw c;  
}  
  
int main() {  
   for ( int i = 1; i >= 0; --i ) {  
      try {  
         if ( i == 1 )  
            GlobalFunction2();  
         if ( i == 0 )  
            GlobalFunction();  
      }  
      catch ( CMyClass& catchC ) {  
         Console::WriteLine( "In 'catch(CMyClass& catchC)'" );  
         Console::WriteLine( catchC.d );  
      }  
      catch ( MyStruct^ catchException ) {  
         Console::WriteLine( "In 'catch(MyStruct^ catchException)'" );  
         Console::WriteLine( catchException->i );  
      }  
   }  
}  
```  
  
### <a name="output"></a>출력  
  
```  
In 'catch(CMyClass& catchC)'  
2  
In 'catch(MyStruct^ catchException)'  
11  
```  
  
### <a name="order-of-unwinding-for-c-objects"></a>C + + 개체에 대 한 해제 순서  
 해제 throw 함수 및 처리 함수 사이 실행 시간에 수 있는 소멸자가 있는 모든 c + + 개체에 대해 발생 합니다. CLR 형식은 힙에 할당 된, 때문에 해제 해도에 적용 되지 않습니다.  
  
 Throw 된 예외에 대 한 이벤트의 순서는 다음과 같습니다.  
  
1.  런타임에 적절 한 catch 절에 대 한 또는 SEH를의 경우 스택 워크는 SEH 예외를 catch 하기에 대 한 필터를 제외 하 고 있습니다. Catch 절 어휘 순서로 먼저 검색 하 고 동적으로 우선 호출 스택.  
  
2.  올바른 처리기 발견 되 면 해당 지점에는 스택 해제 됩니다. 스택의 각 함수 호출에 대 한 로컬 개체 소멸 되 고 가장에서으로 블록이 실행 되는 __finally 바깥쪽 중첩 합니다.  
  
3.  스택의 스택이 해제 되 면 catch 절이 실행 됩니다.  
  
### <a name="catching-unmanaged-types"></a>관리 되지 않는 형식 찾기  
 형식의 예외를 사용 하 여 래핑는 관리 되지 않는 개체 형식 발생 하면 [System::Runtime.InteropServices::SEHException](https://msdn.microsoft.com/en-us/library/system.runtime.interopservices.sehexception.aspx)합니다. 적절 한를 검색할 때 **catch** 절, 두 가지 가능성이 있습니다.  
  
-   네이티브 c + + 형식 발생 하는 경우는 예외가 래핑이 해제 되 고 해당 형식과 비교 합니다. 이 비교는 네이티브 c + + 형식을를 일반적인 방법으로 찾아낼 수 있습니다.  
  
-   그러나 경우는 **catch** 형식의 절을 **SEHException** 또는 해당 기본 클래스 중 하나를 먼저 검사, 절은 예외를 가로챕니다. 따라서 모든 catch 절 CLR 형식의 전에 네이티브 c + + 형식을 먼저 catch 하는 모든 catch 절을 배치 해야 합니다.  
  
 다음 사항에 유의하십시오.  
  
```  
catch(Object^)  
```  
  
 를 갖는  
  
```  
catch(...)  
```  
  
 SEH 예외를 포함 하 여 모든 throw 된 형식을 모두 catch 합니다.  
  
 관리 되지 않는 형식으로 catch(Object^) 들어갈, throw 된 개체는 제거 되지 않습니다.  
  
 관리 되지 않은 예외를 throw 또는 catch 할 때 사용 하는 것이 좋습니다는 [/EHsc](../build/reference/eh-exception-handling-model.md) 대신 컴파일러 옵션 **/EHs** 또는 **/EHa**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [예외 처리](../windows/exception-handling-cpp-component-extensions.md)   
 [safe_cast](../windows/safe-cast-cpp-component-extensions.md)   
 [예외 처리](../cpp/exception-handling-in-visual-cpp.md)