---
title: "__unaligned | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__unaligned_cpp"
  - "__unaligned"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__unaligned 키워드[C++]"
ms.assetid: 0cd83aad-1840-47e3-ad33-59bfcbe6375b
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# __unaligned
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

포인터를 `__unaligned` 한정자로 선언하는 경우, 컴파일러는 포인터가 정렬되지 않은 데이터의 주소 지정한다고 가정합니다.  따라서 IPF\(Itanium Processor Family\) 컴퓨터를 대상으로 하는 응용 프로그램의 경우, 컴파일러는 정렬되지 않은 데이터를 한 번에 1바이트씩 읽는 코드를 생성합니다.  
  
## 설명  
 `__unaligned` 한정자는 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]와 [!INCLUDE[vcpritanium](../cpp/includes/vcpritanium_md.md)] 컴파일러에 대해 유효하지만 IPF 컴퓨터를 대상으로 하는 응용 프로그램에만 영향을 줍니다.  이 한정자는 주소가 지정된 데이터의 정렬만을 설명하며, 포인터 자체는 정렬된 것으로 가정합니다.  
  
 [!INCLUDE[vcpritanium](../cpp/includes/vcpritanium_md.md)] 프로세서가 정렬이 잘못된 데이터에 액세스할 때 정렬 오류가 발생하며 이 오류를 처리하는 시간으로 인해 성능이 저하됩니다.  `__unaligned` 한정자를 사용해 프로세서가 데이터를 한 번에 1 바이트씩 읽도록 하여 오류를 방지합니다.  [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 프로세서를 통해 정렬이 잘못된 데이터가 오류 없이 처리되기 때문에 이 한정자는 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 응용 프로그램에 필요하지 않습니다.  
  
 정렬에 대한 자세한 내용은 다음을 참조하십시오.  
  
-   [맞춤](../cpp/align-cpp.md)  
  
-   [\_\_alignof 연산자](../cpp/alignof-operator.md)  
  
-   [pack](../preprocessor/pack.md)  
  
-   [\/Zp\(구조체 멤버 맞춤\)](../build/reference/zp-struct-member-alignment.md)  
  
-   [구조체 맞춤 예제](../build/examples-of-structure-alignment.md)  
  
## 예제  
  
```  
// unaligned_keyword.cpp  
// compile with: /c  
// processor: x64 IPF  
#include <stdio.h>  
int main() {  
   char buf[100];  
  
   int __unaligned *p1 = (int*)(&buf[37]);  
   int *p2 = (int *)p1;  
  
   *p1 = 0;   // ok  
  
   __try {  
      *p2 = 0;  // throws an exception  
   }  
   __except(1) {  
      puts("exception");  
   }  
}  
```  
  
## 참고 항목  
 [C\+\+ 키워드](../cpp/keywords-cpp.md)