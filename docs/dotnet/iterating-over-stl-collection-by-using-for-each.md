---
title: "각각에 대해 사용 하 여 c + + 표준 라이브러리 컬렉션을 반복 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords: DTL collections, iterating over
ms.assetid: 9358ca29-b982-4a19-bbfd-bef50fe66c9a
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1a4ce2de13380895f1f313559abeb87e4cd65db2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="iterating-over-c-standard-library-collection-by-using-for-each"></a>각각에 대해 사용 하 여 c + + 표준 라이브러리 컬렉션 반복
`for each` c + + 표준 라이브러리 컬렉션을 반복 하는 키워드를 사용할 수 있습니다.  
  
## <a name="all-platforms"></a>모든 플랫폼  
 **주의**  
  
 C + + 표준 라이브러리 컬렉션이 라고도 *컨테이너*합니다. 자세한 내용은 [C++ 표준 라이브러리 컨테이너](../standard-library/stl-containers.md)를 참조하세요.  
  
## <a name="examples"></a>예제  
 **예제**  
  
 다음 코드 예제에서는 `for each` 반복 하는 [ \<지도 >](../standard-library/map.md)합니다.  
  
```  
// for_each_stl.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
#include <string>  
using namespace std;  
  
int main() {  
   int retval  = 0;  
   map<string, int> months;  
  
   months["january"] = 31;  
   months["february"] = 28;  
   months["march"] = 31;  
   months["april"] = 30;  
   months["may"] = 31;  
   months["june"] = 30;  
   months["july"] = 31;  
   months["august"] = 31;  
   months["september"] = 30;  
   months["october"] = 31;  
   months["november"] = 30;  
   months["december"] = 31;  
  
   map<string, int> months_30;  
  
   for each( pair<string, int> c in months )  
      if ( c.second == 30 )  
         months_30[c.first] = c.second;  
  
   for each( pair<string, int> c in months_30 )  
      retval++;  
  
   cout << "Months with 30 days = " << retval << endl;  
}  
```  
  
 **출력**  
  
```Output  
Months with 30 days = 4  
```  
  
 **예제**  
  
 다음 코드 예제에서는 const 참조를 사용 하 여 (`const&`)에 대 한 c + + 표준 라이브러리 컨테이너와 반복 변수입니다. 참조를 사용할 수 있습니다 (`&`)로 선언 될 수 있는 형식의 컬렉션에서 반복 변수로 *T*`&`합니다.  
  
```  
// for_each_stl_2.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
using namespace std;  
  
int main() {  
   int retval = 0;  
  
   vector<int> col(3);  
   col[0] = 10;  
   col[1] = 20;  
   col[2] = 30;  
  
   for each( const int& c in col )  
      retval += c;  
  
   cout << "retval: " << retval << endl;  
}  
```  
  
 **출력**  
  
```Output  
retval: 60  
```  
  
## <a name="windows-runtime"></a>Windows 런타임  
 **주의**  
  
 이 기능에 대 한 플랫폼별 설명이 없습니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/ZW**  
  
## <a name="common-language-runtime"></a>공용 언어 런타임 
 **주의**  
  
 이 기능에 대 한 플랫폼별 설명이 없습니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/clr**  
  
## <a name="see-also"></a>참고 항목  
 [각 항목에 대해에서](../dotnet/for-each-in.md)   
 [런타임 플랫폼용 구성 요소 확장](../windows/component-extensions-for-runtime-platforms.md)