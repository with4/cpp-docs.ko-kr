---
title: "예외 필터 작성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- exception handling [C++], filters
ms.assetid: 47fc832b-a707-4422-b60a-aaefe14189e5
caps.latest.revision: 9
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
ms.openlocfilehash: 07bce97cdac37a920716e72f88bdda2d164fc479
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="writing-an-exception-filter"></a>예외 필터 작성
예외 처리기의 수준으로 이동하거나 계속 실행하여 예외를 처리할 수 있습니다. 예외 및 제어를 처리 하는 예외 처리기 코드를 사용 하는 대신 사용할 수 있습니다 *필터* 문제를 정리 하 고 그런 다음-1을 반환 하 여 스택을 삭제 하지 않고 정상 흐름 재개 하 합니다.  
  
> [!NOTE]
>  일부 예외는 계속할 수 없습니다. 경우 *필터* 평가 시스템을 이러한 예외에 대 한-1로에서 새로운 예외가 발생 합니다. 호출 하는 경우 [RaiseException](http://msdn.microsoft.com/library/windows/desktop/ms680552), 예외를 계속할지 여부를 결정 합니다.  
  
 다음 코드에서 함수 호출을 사용 하는 예를 들어는 *필터* 식:이 함수는 문제를 처리 한 다음 정상적인 제어 흐름을 재개 하려면-1을 반환 합니다.  
  
```  
// exceptions_Writing_an_Exception_Filter.cpp  
#include <windows.h>  
int main() {  
   int Eval_Exception( int );  
  
   __try {}  
  
   __except ( Eval_Exception( GetExceptionCode( ))) {  
      ;  
   }  
  
}  
void ResetVars( int ) {}  
int Eval_Exception ( int n_except ) {  
   if ( n_except != STATUS_INTEGER_OVERFLOW &&   
      n_except != STATUS_FLOAT_OVERFLOW )   // Pass on most exceptions  
   return EXCEPTION_CONTINUE_SEARCH;  
  
   // Execute some code to clean up problem  
   ResetVars( 0 );   // initializes data to 0  
   return EXCEPTION_CONTINUE_EXECUTION;  
}  
```  
  
 함수 호출을 사용 하는 것이 좋습니다는 *필터* 식 때마다 *필터* 아무것도 복잡 한 작업을 수행 해야 합니다. 식을 계산하면 함수가 실행됩니다. 이 경우에는 `Eval_Exception`입니다.  
  
 사용 하 여 [GetExceptionCode](http://msdn.microsoft.com/library/windows/desktop/ms679356) 하 여 예외를 확인 합니다. 필터 자체 내에서 이 함수를 호출해야 합니다. `Eval_Exception`호출할 수 없습니다 **GetExceptionCode**, 없지만 예외 코드를 전달 해야 합니다.  
  
 이 처리기는 예외가 정수 또는 부동 소수점 오버플로가 아닌 경우 제어를 다른 처리기에 전달합니다. 그럴 경우 처리기는 함수(`ResetVars`가 유일한 예이며, API 함수가 아님)를 호출하여 일부 전역 변수를 다시 설정합니다. *문 블록 2*,이 예제에서는 비어 실행 될 수 없습니다 때문에 `Eval_Exception` EXCEPTION_EXECUTE_HANDLER (1)을 반환 하지 않습니다.  
  
 함수 호출 사용은 복잡한 필터 식을 처리하는 좋은 일반 용도의 기술입니다. 유용한 두 개의 다른 C 언어 기능은 다음과 같습니다.  
  
-   조건 연산자  
  
-   쉼표 연산자  
  
 조건 연산자는 특정 반환 코드를 검사한 다음 서로 다른 두 값 중 하나를 반환하는 데 사용될 수 있기 때문에 대개 유용합니다. 예를 들어 다음 코드의 필터는 예외가 `STATUS_INTEGER_OVERFLOW`일 경우에만 예외를 인식합니다.  
  
```  
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ? 1 : 0 ) {  
```  
  
 다음 코드는 동일한 결과를 생성하므로 이 경우 조건 연산자의 목적은 선명도를 제공하는 것입니다.  
  
```  
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ) {  
```  
  
 조건 연산자는-1, EXCEPTION_CONTINUE_EXECUTION으로 계산 되도록 필터를 사용할 수 있는 경우에 보다 유용 합니다.  
  
 쉼표 연산자를 사용하면 단일 식 내의 여러 독립적인 연산을 수행할 수 있습니다. 여러 문을 실행한 다음 마지막 식의 값을 반환하는 효과와 대체로 비슷합니다. 예를 들어 다음 코드는 예외 코드를 변수에 저장한 다음 테스트합니다.  
  
```  
__except( nCode = GetExceptionCode(), nCode == STATUS_INTEGER_OVERFLOW )  
```  
  
## <a name="see-also"></a>참고 항목  
 [예외 처리기 작성](../cpp/writing-an-exception-handler.md)   
 [구조적 예외 처리(C/C++)](../cpp/structured-exception-handling-c-cpp.md)
