---
title: "오류 및 예외 처리(최신 C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: a6c111d0-24f9-4bbb-997d-3db4569761b7
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 오류 및 예외 처리(최신 C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

대부분의 시나리오에서 최신 c + +에서 보고 하 고 논리 오류 및 런타임 오류를 모두 처리 하는 기본 방법은 예외를 사용 하는 합니다. 스택 오류를 감지 하는 함수 및 컨텍스트를 처리 하는 방법을 알고 있는 함수 간의 몇 가지 함수 호출에 있는 경우 특히 유용 합니다. 예외 호출 스택에 대 한 정보를 전달 하는 오류를 감지 하는 코드에 대 한 형식, 잘 정의 된 방법을 제공 합니다.  
  
 프로그램 오류는 일반적으로 두 가지 범주로 나뉩니다: 논리 오류 "네트워크 서비스를 사용할 수 없음" 오류 실수를 예를 들어, "인덱스가 범위를 벗어났습니다" 오류가 프로그래밍과 런타임 오류는 프로그래머의 제어를 벗어난 예를 들어로 인해 발생 합니다. 오류 코드 또는 특정 기능에 대 한 상태 코드를 나타내는 값을 반환 하거나 호출자에 게 오류가 보고 된 되었는지 확인 하는 모든 함수 호출 후 선택적으로 검색할 수 있습니다 하는 전역 변수를 설정 하 여 C 스타일 프로그래밍 및 COM의 관리 오류 보고 합니다. 예를 들어 호출자에 게 오류를 알리기 위해 HRESULT 반환 값을 사용 하는 COM 프로그래밍 및 Win32 API 호출 스택에서 보고 된 마지막 오류를 검색 하려면 GetLastError 함수에 있습니다. 두이 경우 모두에 호출자가 코드를 인식 하 고 적절 하 게 응답할 수 있습니다. 호출자에 게 오류 코드를 명시적으로 처리 하지 않는 경우 프로그램이 경고 없이 크래시 수도 계속 잘못 된 데이터를 사용 하 여 실행 하 고 잘못 된 결과가 있습니다.  
  
 예외는 다음과 같은 이유로 최신 c + +에서 기본 설정:  
  
-   예외가 호출 코드에 오류 조건이 인식 하 고이 처리 하면 됩니다. 처리 되지 않은 예외는 프로그램 실행을 중지 합니다.  
  
-   예외는 오류를 처리할 수 있는 호출 스택에 있는 지점으로 이동 합니다. 중간 함수는 예외 전파를 설정할 수 있습니다. 다른 계층에 맞게 필요가 없습니다.  
  
-   예외 스택 해제 메커니즘 예외가 throw 된 후 잘 정의 된 규칙에 따라 범위에 있는 모든 개체를 삭제 합니다.  
  
-   예외는 오류를 감지 하는 코드 및 오류를 처리 하는 코드를 서로 확실히 구분할 수 있습니다.  
  
 다음은 간단한 예제에는 예외의 throw 및 catch c + +에서에 대 한 필요한 구문을 보여 줍니다.  
  
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
      if(c < numeric_limits<char>::max())  
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
  
 C + +에서 예외를 사용 하면 C# 및 Java와 같은 언어에서 비슷합니다. 에 `try` 예외는 경우 차단 *발생* 됩니다 *발견 되었습니다* 연결 된 첫 번째 `catch` 블록 형식이 일치 하는 예외입니다. 실행이 이동 즉,는 `throw` 문을 `catch` 문입니다. 사용할 수 있는 catch 블록이 없는 경우 `std::terminate` 호출 되 고 프로그램이 종료 됩니다. C + +에서는 모든 형식을 throw 될 수 있습니다. 그러나 좋습니다에서 직접 또는 간접적으로 파생 되는 형식을 throw 하는 `std::exception`합니다. 이전 예제에서는 예외 유형 [invalid_argument](../standard-library/invalid-argument-class.md), 의 표준 라이브러리에 정의 된는 [\< stdexcept>](../standard-library/stdexcept.md) 헤더 파일입니다. C + +는 제공 하지 않으며 필요 하지는 `finally` 블록을 예외가 throw 되 면 모든 리소스가 해제 되었는지 확인 합니다. 자원 수집이 초기화 (RAII) 관용구 스마트 포인터를 사용 하는 리소스를 정리 하기 위해 필요한 기능을 제공 합니다. 자세한 내용은 참조 [하는 방법: 예외 안전성을 위한 디자인](../cpp/how-to-design-for-exception-safety.md)합니다. C + + 스택 해제 메커니즘에 대 한 정보를 참조 하십시오. [예외 및 스택 해제](../cpp/exceptions-and-stack-unwinding-in-cpp.md)합니다.  
  
## <a name="basic-guidelines"></a>기본 지침  
 강력한 오류 처리는 모든 프로그래밍 언어로 어렵습니다. 예외를 처리 하는 좋은 오류를 지 원하는 몇 가지 기능을 제공 하지만 사용자에 대 한 모든 작업을 못합니다. 예외 메커니즘의 장점을 실현 하려면 염두 예외 코드를 디자인 합니다.  
  
-   사용 하 여 어설션 절대 발생 해서는 안 오류를 검사 합니다. 예를 들어 발생할 수 있는 오류에 대 한 공용 함수에서 매개 변수 입력된 유효성 검사의 오류를 확인 하려면 예외를 사용 합니다. 자세한 내용은 섹션을 참조 하십시오. **예외 vs. 어설션**합니다.  
  
-   하나 이상의 중간 함수 호출에 의해 오류를 감지 하는 코드에서 오류를 처리 하는 코드를 구분 될 수 있을 때 예외를 사용 합니다. 오류를 처리 하는 코드를 검색 하는 코드에 밀접 하 게 결합 하는 경우 성능이 중요 한 루프에서 오류 코드를 대신 사용 하 여 사용할지 고려 합니다. 예외를 사용 하지 않는 경우에 대 한 자세한 내용은 참조 [(NOTINBUILD) 하지 않는 경우 예외를 사용 하 여](http://msdn.microsoft.com/ko-kr/e810df8b-2217-4e81-bae5-02f0a69f1346)합니다.  
  
-   Throw 하거나 예외를 전파할 수 있는 모든 함수에 대 한 세 가지 예외 보증 중 하나를 제공 합니다: 강력한 보증, 기본 보증 또는 nothrow (noexcept) 보장 합니다. 자세한 내용은 참조 [하는 방법: 예외 안전성을 위한 디자인](../cpp/how-to-design-for-exception-safety.md)합니다.  
  
-   값으로 예외를 throw, 참조로 catch 하 합니다. 처리할 수 없는 catch 합니다. 자세한 내용은 참조 [(NOTINBUILD) 발생 하 고 지침을 catch 할 예외 (c + +)](http://msdn.microsoft.com/ko-kr/0a9b0a3a-64c5-43f5-a080-fca69b89e839)합니다.  
  
-   C + + 11에서 사용 되는 예외 사양 사용 하지 마십시오. 자세한 내용은 섹션을 참조 하십시오. **예외 사양 및 noexcept**합니다.  
  
-   적용 되는 경우 예외 형식은 표준 라이브러리를 사용 합니다. 사용자 지정 예외 형식을 파생할는 [exception 클래스](../standard-library/exception-class1.md) 계층 구조입니다. 자세한 내용은 참조 [(NOTINBUILD) 하는 방법: 표준 라이브러리 예외 개체를 사용 하 여](http://msdn.microsoft.com/ko-kr/ad1fb785-ed4e-4d94-8e84-964353aed7b6)합니다.  
  
-   소멸자에서 이스케이프 처리 하거나 메모리 할당 해제 함수에 대 한 예외를 허용 안 함.  
  
## <a name="exceptions-and-performance"></a>예외 및 성능  
 예외 메커니즘 최소한 기능은 성능을 예외가 throw 됩니다. 예외가 throw 되 면 스택 탐색의 비용 및 해제는 함수 호출의 비용을 거의 유사 합니다. 추가 데이터 구조는 이후 호출 스택을 추적 하는 데 필요한는 `try` 블록을 입력 하 고 추가 지침은 예외가 발생 하는 경우 스택 해제 해야 합니다. 그러나 대부분의 시나리오에서 성능 및 메모리 사용 공간 비용이 중요 하지 않습니다. 예외 성능에 악영향 가능성이 매우 메모리 제한 된 시스템에만 중요 한 것으로 되었거나에서 성능이 중요 한 루프는 오류가 정기적으로 발생할 수이 고이 처리 하는 코드는 밀접 하 게 보고 하는 코드에 있습니다. 어떤 경우 프로 파일링 하 고 측정 하지 않고 예외의 실제 비용을 알 수는 없습니다. 드문 경우에도 비용, 중요 한 경우에 향상 된 정확성, 더 쉽게 유지 관리의 편의성 및 잘 설계 된 예외 정책에 의해 제공 되는 다른 이점을 이용에 대해 검토 수 있습니다.  
  
## <a name="exceptions-vs-assertions"></a>어설션 및 예외  
 예외와 어설션을 프로그램에서 런타임 오류를 감지 하는 두 가지 메커니즘이 있습니다. 사용 조건에 대 한 모든 코드가 정확한 경우 true이 아니어야 하는 개발 중 테스트에 어설션 합니다. 오류 수정 해야 하는 코드에서 무언가 나타내기 때문에 예외를 사용 하 여 이러한 오류를 처리에 포인터가 없는 및 프로그램 실행 시에서 복구 하는 조건을 나타내지 않습니다. 디버거에서; 프로그램 상태를 검사할 수 있도록 assert 문에서 실행을 중지 예외는 첫 번째 적절 한 catch 처리기의 실행이 계속 됩니다. 예외를 사용 하 여 경우에 코드가 올바른지, 예를 들어 "파일 not found" 또는 "메모리가 부족 합니다." 실행 시 발생할 수 있는 오류 조건 확인 방금 복구 로그로 메시지를 출력 한 프로그램을 종료 하는 경우에 이러한 조건에서 복구 하려고 합니다. 항상 예외를 사용 하 여 공용 함수에 대 한 인수를 확인 합니다. 사용자가 함수 이면 오류가 없는 경우에 사용자 전달할 수 있는 인수를 완전히 제어할이 없을 수 있습니다.  
  
## <a name="c-exceptions-versus-windows-seh-exceptions"></a>Windows의 SEH 예외와 c + + 예외  
 C 및 c + + 프로그램에는 구조적된 예외 처리 (SEH) 메커니즘 Windows 운영 체제에서 사용할 수 있습니다. SEH에 설명 된 개념 비슷한 c + + 예외를 SEH를 사용 한다는 점을 제외 하면는 `__try`, `__except`, 및 `__finally` 대신 생성 `try` 및 `catch`합니다. Visual c + +, c + + 예외는 SEH에 대 한 구현 됩니다. 그러나 c + + 코드를 작성 하는 경우에 c + + 예외 구문을 사용 합니다.  
  
 SEH에 대 한 자세한 내용은 참조 [구조적 예외 처리 (C/c + +)](../cpp/structured-exception-handling-c-cpp.md)합니다.  
  
## <a name="exception-specifications-and-noexcept"></a>예외 사양 및 noexcept  
 예외 사양 함수에서 throw 할 수 있는 예외를 지정 하는 방법으로 c + +에서 도입 되었습니다. 그러나 예외 사양 실제로 문제가 있는 입증 하 고 C + + 11 초안 표준에서 지원 되지 않습니다. 제외 하 고 예외 사양 사용 하지 않는 것이 좋습니다 `throw()`, 예외 없습니다 벗어나는 예외를 허용 하는지 나타냅니다. 형식의 예외 사양 사용 해야 할 경우 `throw(`*형식*`)`, 를 알고 있어야 하는 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 다양 한 방식으로 표준에서 필수입니다. 자세한 내용은 참조 [예외 사양 (throw)](../cpp/exception-specifications-throw-cpp.md)합니다.  `noexcept` 지정자를 기본 설정 대신 C + + 11에 도입 `throw()`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 예외 및 비 예외 코드 간 인터페이스](../cpp/how-to-interface-between-exceptional-and-non-exceptional-code.md)   
 [C + +의 진화](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C + + 언어 참조](../cpp/cpp-language-reference.md)   
 [C + + 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)