---
title: "for each를 사용하여 STL 컬렉션 반복 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DTL 컬렉션, 반복 처리"
ms.assetid: 9358ca29-b982-4a19-bbfd-bef50fe66c9a
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# for each를 사용하여 STL 컬렉션 반복
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The `for each` keyword can be used to iterate over a Standard C\+\+ Library \(STL\) collection.  
  
## 모든 플랫폼  
 **설명**  
  
 An STL collection is also known as a *container*.  자세한 내용은 [STL 컨테이너](../standard-library/stl-containers.md)을 참조하십시오.  
  
## 예제  
 **예제**  
  
 The following code example uses `for each` to iterate over a [\< 맵 \>](../standard-library/map.md).  
  
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
  
 **Output**  
  
  **Months with 30 days \= 4** **예제**  
  
 The following code example uses a const reference \(`const&`\) for an iteration variable with STL containers.  You can use a reference \(`&`\) as an iteration variable on any collection of a type that can be declared as a *T*`&`.  
  
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
  
 **Output**  
  
  **retval: 60**   
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **설명**  
  
 There are no platform\-specific remarks about this feature.  
  
### 요구 사항  
 컴파일러 옵션: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **설명**  
  
 There are no platform\-specific remarks about this feature.  
  
### 요구 사항  
 컴파일러 옵션: **\/clr**  
  
## 참고 항목  
 [for each, in](../dotnet/for-each-in.md)   
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)