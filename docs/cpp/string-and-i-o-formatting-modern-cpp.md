---
title: "문자열 및 I/o 서식 (최신 c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 3954e8de-a59b-4175-89c9-4ee842ab89ed
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a13861fe03547e37c4de72c21a528e297a217511
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="string-and-io-formatting-modern-c"></a>문자열 및 I/O 서식 지정(최신 C++)
C + + [iostreams](../standard-library/iostream.md) 서식이 지정 된 문자열 I/O 수 있습니다. 예를 들어 다음 코드를 보여 줍니다 출력 16 진수, 먼저 현재 상태를 저장 하 고 다시 상태 서식을 cout에 전달 되 고 나면 이런 방식으로 한 줄에 대 한 뿐 아니라 변경 될 때까지 유지 됩니다 때문에 이후에 설정 하는 정수에 서식을 지정 하려면 cout를 설정 하는 방법 코드입니다.  
  
```cpp  
#include <iostream>  
#include <iomanip>  
  
using namespace std;  
  
int main()   
{  
    ios state(nullptr);  
  
    cout << "The answer in decimal is: " << 42 << endl;  
  
    state.copyfmt(cout); // save current formatting  
    cout << "In hex: 0x" // now load up a bunch of formatting modifiers  
        << hex   
        << uppercase   
        << setw(8)   
        << setfill('0')   
        << 42            // the actual value we wanted to print out  
        << endl;  
    cout.copyfmt(state); // restore previous formatting  
}  
  
```  
  
 완전히 수 대부분의 경우에서 너무 복잡 합니다. 대신 비표준 이더라도 부스트 c + + 라이브러리에서 Boost.Format 사용할 수 있습니다. 모든 부스트 라이브러리에서 다운로드할 수 있습니다는 [부스트](http://www.boost.org/) 웹 사이트입니다.  
  
 Boost.Format의 일부 이점은 다음과 같습니다.  
  
-   안전한: 형식이 안전한 오류에 대 한 예외를 throw 하 고-예를 들어 너무 적거나 너무 많은 항목의 사양입니다.  
  
-   스트림 될 수 있는 모든 형식에 대 한 확장 가능한: 작동 합니다.  
  
-   편리한: 표준 Posix 및 유사한 형식 문자열입니다.  
  
 Boost.Format c + +는 기반으로 하지만 [iostreams](../standard-library/iostream-programming.md), 성능이 최적화 하지 않을 안전 하 고 확장 가능 합니다. 성능 최적화를 필요로 하는 경우 고려 C [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) 및 [sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md), 빠른 되며 사용 하기 쉽습니다. 그러나 없는 확장 없거나 취약점 으로부터 안전 하 게 보호 합니다. (안전한 버전이 존재 하지만 그로 인해 약간의 성능 저하가 발생 합니다. 자세한 내용은 참조 [printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md) 및 [sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)).  
  
 다음 코드 서식 지정 기능 향상의 일부를 보여 줍니다.  
  
```cpp  
    string s = str( format("%2% %2% %1%\n") % "world" % "hello" );  
    // s contains "hello hello world"    
  
    for( auto i = 0; i < names.size(); ++i )  
        cout << format("%1% %2% %|40t|%3%\n") % first[i] % last[i] % tel[i];  
    // Georges Benjamin Clemenceau             +33 (0) 123 456 789  
    // Jean de Lattre de Tassigny              +33 (0) 987 654 321  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [C + +의 진화](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C + + 언어 참조](../cpp/cpp-language-reference.md)   
 [C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)   
 [\<iostream >](../standard-library/iostream.md)   
 [\<제한 >](../standard-library/limits.md)   
 [\<iomanip>](../standard-library/iomanip.md)
