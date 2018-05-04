---
title: 문 (c + +) 전환 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- default_cpp
- switch_cpp
- case_cpp
dev_langs:
- C++
helpviewer_keywords:
- switch keyword [C++]
- case keyword [C++], in switch statements
- default keyword [C++]
ms.assetid: 6c3f3ed3-5593-463c-8f4b-b33742b455c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5cea2c7e4bff895f9ccabc044ed5b7f5ae506b32
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="switch-statement-c"></a>switch 문 (C++)
정수 계열 식의 값에 따라 코드의 여러 섹션 중에서 선택할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
   switch ( init; expression )  
   case constant-expression : statement  
   [default  : statement]  
```  
  
## <a name="remarks"></a>설명  
 *식* 정수 계열 형식 또는 정수 계열 형식으로 명확한 변환이 되는 클래스 형식 이어야 합니다. 에 설명 된 대로 정수 계열 확장은 수행 되며 [표준 변환](standard-conversions.md)합니다.  
  
 `switch` 문 본문이 일련의 구성 **대/소문자** 레이블과 선택적 **기본** 레이블. 없는 두 상수 식도 **대/소문자** 문은 동일한 값으로 계산할 수 있습니다. **기본** 레이블은 한 번만 나타날 수 있습니다. 레이블 문은 구문적 요구 사항이 아니지만 `switch` 문은 레이블 문이 없으면 의미가 없습니다.   기본 문은 끝에 오지 않아도 되며 switch 문의 본문 중 어느 위치에나 나타날 수 있습니다. case 또는 default 레이블은 switch 문 내에만 나타날 수 있습니다.  
  
 *문* 각 **대/소문자** 레이블의 유형으로 변환할 *식* 와 비교 하 고 *식* 에 대 한 같음입니다. 해당 문으로 제어가 전달 **대/소문자** *문* 의 값과 일치 *식*합니다. 결과적으로 발생하는 동작은 다음 표에 나와 있습니다.  
  
### <a name="switch-statement-behavior"></a>switch 문 동작  
  
|조건|작업|  
|---------------|------------|  
|변환된 값이 승격된 제어 식의 값과 일치합니다.|제어가 해당 레이블 뒤에 오는 문으로 전송됩니다.|  
|상수 조건과 일치 하는 상수는 **대/소문자** 레이블의 **기본** 레이블이 있습니다.|제어가 **기본** 레이블.|  
|상수 조건과 일치 하는 상수는 **대/소문자** 레이블의 **기본** 레이블이 나타나지 않습니다.|제어가 `switch` 문 뒤의 문으로 전송됩니다.|  
  
 이후 제어가 방해 되지 않습니다는 일치 하는 식이 발견 되는 경우 **대/소문자** 또는 **기본** 레이블을 합니다. [나누기](../cpp/break-statement-cpp.md) 문을 사용 실행을 중지 하 고 뒤의 문으로 제어를 전송 하는 `switch` 문. 없이 **나누기** 문, 일치 하는 모든 문을 **대/소문자** 의 끝에 레이블은 `switch`를 포함 하 여는 **기본**, 실행 됩니다. 예를 들어:  
  
```  
// switch_statement1.cpp  
#include <stdio.h>  
  
int main() {  
   char *buffer = "Any character stream";  
   int capa, lettera, nota;  
   char c;  
   capa = lettera = nota = 0;  
  
   while ( c = *buffer++ )   // Walks buffer until NULL  
   {  
      switch ( c )  
      {  
         case 'A':  
            capa++;  
            break;  
         case 'a':  
            lettera++;  
            break;  
         default:  
            nota++;  
      }  
   }  
   printf_s( "\nUppercase a: %d\nLowercase a: %d\nTotal: %d\n",  
      capa, lettera, (capa + lettera + nota) );  
}  
```  
  
 위의 예제에서 `capa`는 `c`가 대문자 `A`인 경우 증가됩니다. `break` 뒤의 `capa++` 문이 `switch` 문 본문의 실행을 종료하고 제어를 `while` 루프로 전달합니다. 없이 `break` 문의 실행은 "이동" 다음 레이블 문으로 있도록 `lettera` 및 `nota` 도 증가 됩니다. `break`에 대한 `case 'a'` 문도 비슷한 역할을 합니다. `c`가 소문자 `a`인 경우 `lettera`가 증가하고 `break` 문이 `switch` 문 본문을 종료합니다. `c`가 `a` 또는 `A`가 아닌 경우 `default` 문이 실행됩니다.  

 **2017 이상 visual Studio:** (사용할 수 있는 [/std:c + + 17](../build/reference/std-specify-language-standard-version.md))는 `[[fallthrough]]` C + + 17 표준에 특성을 지정 합니다. 사용할 수는 `switch` 문을 해당 fall 통해 동작이 지정 된 컴파일러에 (또는 코드를 읽는 사람에 게) 힌트로 합니다. Visual c + + 컴파일러 현재 경고 하지 않습니다 fallthrough 동작에 있으므로이 특성에 영향을 주지 컴파일러 동작이 없습니다. 특성이 빈 문을; labeled 문 내에 적용 되는 참고 즉 세미콜론은 필요 합니다.

```cpp
int main()
{
    int n = 5;
    switch (n)
    {

    case 1:
        a();
        break;
    case 2:
        b();
        d();
        [[fallthrough]]; // I meant to do this!
    case 3:
        c();
        break;
    default:
        d();
        break;
    }

    return 0;
}
```

 **Visual Studio 2017 15.3 이상 버전** (사용할 수 있는 [/std:c + + 17](../build/reference/std-specify-language-standard-version.md)): switch 문에 소개 하 고 범위가 switch 문의 제한 된 변수를 초기화할 수 있습니다.

```cpp
 switch (Gadget gadget(args); auto s = gadget.get_status())
        {
        case status::good:
            gadget.zip();
            break;
        case status::bad:
            throw BadGadget();
        };
```

 `switch` 문의 내부 블록은 도달할 수 있는 한, 즉 가능한 모든 실행 경로에 의해 건너뛰어지지 않는 한 초기화를 사용하는 정의를 포함할 수 있습니다. 이러한 선언을 사용하여 정의된 이름에는 로컬 범위가 있습니다. 예를 들어:  
  
```cpp  
// switch_statement2.cpp  
// C2360 expected  
#include <iostream>  
using namespace std;  
int main(int argc, char *argv[])  
{  
   switch( tolower( *argv[1] ) )  
   {  
       // Error. Unreachable declaration.  
       char szChEntered[] = "Character entered was: ";  
  
   case 'a' :  
       {  
       // Declaration of szChEntered OK. Local scope.  
       char szChEntered[] = "Character entered was: ";  
       cout << szChEntered << "a\n";  
       }  
       break;  
  
   case 'b' :  
       // Value of szChEntered undefined.  
       cout << szChEntered << "b\n";  
       break;  
  
   default:  
       // Value of szChEntered undefined.  
       cout << szChEntered << "neither a nor b\n";  
       break;  
   }  
}  
```  
  
 `switch` 문은 중첩될 수 있습니다. 이러한 경우 **대/소문자** 또는 **기본** 가장 가까운 바깥쪽에 레이블을 연결 `switch` 문에 합니다.  

 
## <a name="microsoft-specific"></a>Microsoft 전용  
 Microsoft C는 `switch` 문의 case 값 수를 제한하지 않습니다. 이 수는 사용 가능한 메모리에 의해서만 제한됩니다. ANSI C의 경우 `switch` 문에서 257개 이상의 case 레이블이 허용되어야 합니다.  
  
 기본적으로 Microsoft C에는 Microsoft 확장을 사용하도록 설정되어 있습니다. 사용 하 여는 [/Za](../build/reference/za-ze-disable-language-extensions.md) 컴파일러 옵션을 이러한 확장을 사용 하지 않도록 설정 합니다.  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [선택 문](../cpp/selection-statements-cpp.md)   
 [키워드](../cpp/keywords-cpp.md)   
 