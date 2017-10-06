---
title: "시도, throw 및 catch 문 (c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- catch_cpp
- try_cpp
- throw_cpp
dev_langs:
- C++
helpviewer_keywords:
- catch keyword [C++]
- keywords [C++], exception handling
- C++ exception handling, statement syntax
- try-catch keyword [C++], about try-catch exception handling
- throw keyword [C++]
- try-catch keyword [C++]
- try-catch keyword [C++], exception handling
- throwing exceptions [C++], throw keyword
- try-catch keyword [C++], throw keyword [C++]s
- throwing exceptions [C++], implementing C++ exception handling
- throwing exceptions [C++]
- throw keyword [C++], throw() vs. throw(...)
ms.assetid: 15e6a87b-b8a5-4032-a7ef-946c644ba12a
caps.latest.revision: 24
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 89db418a92239460379d1ea41d2d49a8073095c2
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="try-throw-and-catch-statements-c"></a>Try, Throw 및 Catch 문(C++)
C++에서 예외 처리를 구현하려면 `try`, `throw` 및 `catch` 식을 사용합니다.  
  
 먼저 `try` 블록을 사용하여 예외를 throw할 수 있는 하나 이상의 문을 포함합니다.  
  
 `throw` 식은 대부분 오류인 예외적인 조건이 `try` 블록에서 발생했음을 나타냅니다. 모든 형식의 개체를 `throw` 식의 피연산자로 사용할 수 있습니다. 일반적으로 이 개체는 일반적으로 오류 정보를 전달하는 데 사용됩니다. 대부분의 경우에서 사용 하는 권장는 [std:: exception](../standard-library/exception-class.md) 클래스 또는 표준 라이브러리에 정의 된 파생된 클래스 중 하나입니다. 그 중 하나가 적합하지 않은 경우 `std::exception`에서 사용자 고유의 예외를 파생하는 것이 좋습니다.  
  
 Throw할 수 있는 예외를 처리하려면 `catch` 블록 바로 다음에 나오는 `try` 블록을 하나 이상 구현합니다. 각 `catch` 블록은 처리할 수 있는 예외 형식을 지정합니다.  
  
 이 예제에서는 `try` 블록과 해당 처리기를 보여 줍니다. `GetNetworkResource()`가 네트워크 연결을 통해 데이터를 받고 두 개의 예외 형식은 `std::exception`에서 파생된 사용자 정의 클래스라고 가정합니다. 예외는 `const` 문의 `catch` 참조를 통해 catch됩니다. 값으로 예외를 throw하고 상수 참조로 catch하는 것이 좋습니다.  
  
## <a name="example"></a>예제  
  
```  
  
MyData md;  
try {  
   // Code that could throw an exception  
   md = GetNetworkResource();  
}  
catch (const networkIOException& e) {  
   // Code that executes when an exception of type  
   // networkIOException is thrown in the try block  
   // ...  
   // Log error message in the exception object  
   cerr << e.what();  
}  
catch (const myDataFormatException& e) {  
   // Code that handles another exception type  
   // ...  
   cerr << e.what();  
}  
  
// The following syntax shows a throw expression  
MyData GetNetworkResource()  
{  
   // ...  
   if (IOSuccess == false)  
      throw networkIOException("Unable to connect");  
   // ...  
   if (readError)  
      throw myDataFormatException("Format error");   
   // ...  
}  
```  
  
## <a name="remarks"></a>설명  
 `try` 절 뒤에 오는 코드는 보호된 코드 섹션입니다. `throw` 식 *throw*-발생-예외입니다. `catch` 절 뒤에 오는 코드 블록은 예외 처리기입니다. 처리기입니다는 *catch* 경우 throw 되는 예외의 형식을 `throw` 및 `catch` 호환 되는 식입니다. 형식 일치를 제어 하는 규칙의 목록에 대 한 `catch` 블록 참조 [어떻게 Catch 블록의 평가](../cpp/how-catch-blocks-are-evaluated-cpp.md)합니다. `catch` 문이 형식 대신 줄임표(...)를 지정하는 경우 `catch` 블록이 모든 형식의 예외를 처리합니다. 로 컴파일할 때는 [/EHa](../build/reference/eh-exception-handling-model.md) 옵션을 C 구조적 예외 및 메모리 보호, 0으로 나누기 및 부동 소수점 위반 등 시스템에서 생성 된 또는 응용 프로그램에서 생성 된 비동기 예외를 포함할 수 있습니다 이러한 . `catch` 블록은 일치하는 형식을 찾기 위해 프로그램 순서에서 처리되기 때문에 줄임표 처리기는 연결된 `try` 블록의 마지막 처리기여야 합니다. `catch(...)`를 주의해서 사용하십시오. catch 블록이 catch되는 특정 예외를 처리하는 방법을 알고 있는 경우가 아니면 프로그램을 계속 실행하지 마십시오. 일반적으로 `catch(...)` 블록은 오류를 기록하고 프로그램 실행을 중지하기 전에 특별한 정리 작업을 수행하는 데 사용합니다.  
  
 피연산자가 없는 `throw` 식은 현재 처리되고 있는 예외를 다시 throw합니다. 예외를 다시 throw할 때 원래 예외의 다형 형식 정보를 보존하므로 이 폼을 사용하는 것이 좋습니다. 이 같은 수식은 `catch` 처리기 또는 `catch` 처리기에서 호출된 함수에만 사용됩니다. 다시 throw된 예외 개체는 복사본이 아닌 원본 예외 개체입니다.  
  
```  
try {  
   throw CSomeOtherException();  
}  
catch(...) {  
   // Catch all exceptions - dangerous!!!  
   // Respond (perhaps only partially) to the exception, then  
   // re-throw to pass the exception to some other handler  
   // ...  
   throw;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [C + + 예외 처리](../cpp/cpp-exception-handling.md)   
 [키워드](../cpp/keywords-cpp.md)   
 [처리 되지 않은 c + + 예외](../cpp/unhandled-cpp-exceptions.md)   
 [__uncaught_exception](../c-runtime-library/reference/uncaught-exception.md)
