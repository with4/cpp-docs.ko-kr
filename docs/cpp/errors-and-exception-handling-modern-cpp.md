---
title: 오류 및 예외 처리 (최신 c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a6c111d0-24f9-4bbb-997d-3db4569761b7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 94a9e75770e822c89ea65a745a2fca491f175d95
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34569864"
---
# <a name="errors-and-exception-handling-modern-c"></a>오류 및 예외 처리(최신 C++)
대부분의 시나리오에서 최신 c + +에서 보고 하 고 논리 오류 및 런타임 오류를 모두 처리 하는 기본 방법은 예외를 사용 하는입니다. 스택에 오류를 검색 하는 함수와 처리 하는 방법을 알고 컨텍스트를 가진 함수를 여러 개의 함수 호출 포함 될 수 있습니다 때 특히 유용 합니다. 예외 호출 스택에 대 한 정보를 전달 하는 오류를 감지 하는 코드에 대 한 정식는 잘 정의 된 방법을 제공 합니다.  
  
 프로그램 오류는 일반적으로 두 가지 범주로 나뉩니다: 한 "network service 사용할 수 없음" 실수, 예를 들어 프로그래밍, "인덱스가 범위를 벗어났습니다" 오류가 및 런타임 오류는 프로그래머의 제어할 수 없는 등으로 인해 논리 오류 오류가 발생 했습니다. 오류 코드 또는 특정 기능에 대 한 상태 코드를 나타내는 값을 반환 하 여 또는 호출자에 게 확인 하려면 모든 함수 호출 후 필요에 따라 검색할 수 있습니다 하는 전역 변수를 설정 하 여 오류 보고 관리 C 스타일 프로그래밍 및 COM 여부 오류가 보고 되었습니다. 예를 들어 COM 프로그래밍 HRESULT 반환 값을 사용 하 여 호출자에 게 오류를 알리기 위해 있으며 Win32 API 호출 스택에서 보고 된 마지막 오류를 검색 하려면 GetLastError 함수입니다. 이러한 경우 모두가 호출자가 코드를 인식 하 고 적절 하 게 응답할 수 있습니다. 호출자에 게 오류 코드를 명시적으로 처리 하지 않는 경우 프로그램이 경고 없이 크래시 또는 잘못 된 데이터와 함께 실행 하 고 잘못 된 결과 생성할 계속 될 수 있습니다.  
  
 예외는 다음과 같은 이유로 현대적인 c + + 기본 설정:  
  
-   예외가 호출 코드 오류 상태를 인식 하 고 처리를 강제로 수행 합니다. 처리 되지 않은 예외는 프로그램 실행을 중지 합니다.  
  
-   예외 오류를 처리할 수 있는 호출 스택에 있는 위치로 이동 합니다. 중간 함수 전파 하는 예외를 설정할 수 있습니다. 다른 레이어와 조정할 필요가 없습니다.  
  
-   예외 스택 해제 메커니즘에서 예외가 throw 된 후 잘 정의 된 규칙에 따라 범위에 있는 모든 개체를 제거 합니다.  
  
-   예외 오류를 감지 하는 코드와 오류를 처리 하는 코드 간의 확실히 구분할 수 있습니다.  
  
 다음은 간단한 예제에는 throw 하 고 c + +에서 예외를 catch에 대 한 필요한 구문을 보여 줍니다.  
  
```cpp  
#include <stdexcept>  
#include <limits>  
#include <iostream>  
  
using namespace std;  
class MyClass  
{  
public:  
   void MyFunc(char c)  
   {  
      if(c > numeric_limits<char>::max())  
         throw invalid_argument("MyFunc argument too large.");  
      //...  
   }  
};  
  
int main()  
{  
   try  
   {  
      MyFunc(256); //cause an exception to throw  
   }  
  
   catch(invalid_argument& e)  
   {  
      cerr << e.what() << endl;  
      return -1;  
   }  
   //...  
   return 0;  
}  
  
```  
  
 C + +에서 예외에서는 C#과 Java와 같은 언어의 구문과 유사합니다. `try` 예외가 발생 하는 경우 차단 *발생* 됩니다 *발견* 첫 번째 연결 `catch` 블록 형식이 일치 하는 예외입니다. 실행이 이동 즉,는 `throw` 문을 `catch` 문. 사용할 수 있는 catch 블록이 없는 경우 `std::terminate` 호출 되 고 프로그램이 종료 됩니다. C + +에서는 모든 형식을 throw 될 수 있습니다. 하지만 직접 또는 간접적으로 파생 되는 형식을 throw 하는 권장 `std::exception`합니다. 이전 예제에서는 예외 유형 [invalid_argument](../standard-library/invalid-argument-class.md)에서 표준 라이브러리에 정의 된는 [ \<stdexcept >](../standard-library/stdexcept.md) 헤더 파일입니다. C + +는 제공 하지 않으며 필요 하지는 `finally` 블록에서 예외가 throw 되 면 모든 리소스가 해제 되도록 합니다. 자원 수집이 초기화 (RAII) 관용구 스마트 포인터를 사용 하는 리소스 정리에 필요한 기능을 제공 합니다. 자세한 내용은 참조 [하는 방법: 예외 안전성을 위한 디자인](../cpp/how-to-design-for-exception-safety.md)합니다. C + + 스택 해제 메커니즘에 대 한 정보를 참조 하십시오. [예외 및 스택 해제](../cpp/exceptions-and-stack-unwinding-in-cpp.md)합니다.  
  
## <a name="basic-guidelines"></a>기본 지침  
 강력한 오류 처리는 프로그래밍 언어의 어려운입니다. 예외 좋은 오류 처리를 지 원하는 몇 가지 기능을 제공 하지만 있습니다에 대 한 모든 작업을 수행할 수 없습니다. 예외 메커니즘의 이점을 실현 하려면 염두 예외 코드를 디자인 합니다.  
  
-   사용 하 여 어설션 발생 하지 않습니다 오류를 검사 합니다. 오류를 검사 하려면 예를 들어 발생할 수 있는 오류에 대 한 공용 함수에서 매개 변수 입력된 유효성 검사의 예외를 사용 합니다. 자세한 내용은 섹션을 참조 하십시오. **예외 대. 어설션**합니다.  
  
-   오류를 처리 하는 코드는 오류를 검색 하는 코드에서 하나 이상의 중간 함수 호출에 의해 구분 될 수 있습니다 때 예외를 사용 합니다. 코드가 오류를 처리 하는 것을 감지 하는 코드에 밀접 하 게 결합 하면 성능이 중요 한 루프에서 오류 코드 대신 사용할 수도 있습니다. 
  
-   Throw 하거나 예외를 전파할 수 있는 모든 함수에 대 한 세 가지 예외 보증 중 하나를 제공: 강력한 보증, 기본 보증 또는 nothrow (noexcept) 보장 합니다. 자세한 내용은 참조 [하는 방법: 예외 안전성을 위한 디자인](../cpp/how-to-design-for-exception-safety.md)합니다.  
  
-   값으로 예외를 throw, 참조로 catch 합니다. 처리할 수 없는 catch 하지 마십시오. 
  
-   C + + 11에서 되지 않는 예외 사양 사용 하지 마십시오. 자세한 내용은 섹션을 참조 하십시오. **예외 사양 및 noexcept**합니다.  
  
-   적용 했을 때 표준 라이브러리 예외 형식을 사용 합니다. 사용자 지정 예외 형식에서 파생 되는 [exception 클래스](../standard-library/exception-class.md) 계층 구조입니다.  
  
-   소멸자에서 이스케이프 또는 메모리 할당 해제 함수에 대 한 예외를 허용 하지 않음.  
  
## <a name="exceptions-and-performance"></a>예외 및 성능  
 예외 메커니즘 중지가 최소화 기능은 성능을 예외가 throw 됩니다. 예외가 발생 하는 경우 스택 탐색의 비용 및 해제는 함수 호출의 비용 거의 유사 합니다. 추가 데이터 구조는 이후 호출 스택을 추적 하는 데 필요한는 `try` 블록을 입력 하 고 예외가 발생 하는 경우 스택 해제 하는 데 필요한 추가 지침입니다. 그러나 대부분의 시나리오에서 성능 및 메모리 사용 비용이 중요 하지 않습니다. 예외 성능에 좋지 않은 영향 가능성이 매우 메모리 제한 된 시스템 에서만 중요 한 것으로 되었거나에서 성능이 중요 한 루프 여기서 오류가 정기적으로 발생 하 고 처리 하는 코드는 밀접 하 게 보고 하는 코드에 있습니다. 어떤 경우 프로 파일링 하 고 측정 하지 않고 예외의 실제 비용을 알 수는 없습니다. 드문 경우에도 비용이 중요는 때에 증가 된 정확성, 더 쉽게 유지 관리의 편의성 및 잘 디자인 된 예외 정책에 의해 제공 되는 다른 이점을 이용에 대해 검토 수 있습니다.  
  
## <a name="exceptions-vs-assertions"></a>어설션 및 예외  
 예외와 어설션을 프로그램에서 런타임 오류를 확인 하기 위한 두 가지 메커니즘이 있습니다. 사용 조건에 대 한 모든 코드 올바르면 true 없어야 하는 개발 중 테스트에 어설션 합니다. 이러한 오류를 수정 해야 하는 코드에 오류가 나타내므로 예외를 사용 하 여 처리에 포인터가 없는 및 프로그램 실행 시에서 복구 하는 조건을 나타내지 않습니다. 디버거에서; 프로그램 상태를 검사할 수 있도록 assert 문에서 실행을 중지 예외는 첫 번째 적절 한 catch 처리기의 실행을 계속 합니다. 예외를 사용 하 여 코드 예를 들어 "파일 찾을 수 없음" 올바른 경우에 또는 "메모리 부족 합니다." 실행 시 발생할 수 있는 오류 조건을 확인합니다 복구만 로그에 메시지를 출력 하 고 프로그램을 종료 하는 경우에 이러한 조건에서 복구 할 수 있습니다. 항상 예외를 사용 하 여 공용 함수에 대 한 인수를 확인 합니다. 사용자가 함수 이면 오류가 없는 경우에 사용자 수를 전달 하는 인수를 완전히 제어할이 없을 수 있습니다.  
  
## <a name="c-exceptions-versus-windows-seh-exceptions"></a>Windows의 SEH 예외와 c + + 예외  
 C 및 c + + 프로그램 구조적된 예외 처리 (SEH)는 Windows 운영 체제에서 제공 되는 메커니즘을 사용할 수 있습니다. SEH의 개념을 비슷한 c + + 예외를 제외 하 고 사용 하 여 SEH는 `__try`, `__except`, 및 `__finally` 대신 생성 `try` 및 `catch`합니다. Visual c + +, c + + 예외는 SEH에 대 한 구현 됩니다. 그러나 c + + 코드를 작성 하는 경우에 c + + 예외 구문을 사용 합니다.  
  
 SEH에 대 한 자세한 내용은 참조 [구조적 예외 처리 (C/c + +)](../cpp/structured-exception-handling-c-cpp.md)합니다.  
  
## <a name="exception-specifications-and-noexcept"></a>예외 사양 및 noexcept  
 예외 사양 함수에서 throw 할 수 있는 예외를 지정 하는 방법으로 c + +에서 도입 되었습니다. 그러나 예외 사양 실제로 문제가 있는 입증 하 고 C + + 11 초안 표준에서 사용 되지 않습니다. 예외 사양을 제외 하 고 사용 하지 않는 것이 좋습니다 `throw()`, 함수 예외가 이스케이프를 허용 하는지 나타냅니다. 예외 사양 형식를 사용 해야 할 경우 `throw(` *형식*`)`, Visual c + +는 표준에서 다양 한 방식으로 필수는 점에 유의 합니다. 자세한 내용은 참조 [예외 사양 (throw)](../cpp/exception-specifications-throw-cpp.md)합니다. `noexcept` 하 기본 설정 대신 지정자는 C + + 11에서 도입 되었습니다 `throw()`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 예외 및 비 예외 코드 간의 인터페이스](../cpp/how-to-interface-between-exceptional-and-non-exceptional-code.md)   
 [C + +의 진화](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ 언어 참조](../cpp/cpp-language-reference.md)   
 [C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)
