---
title: __unaligned | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: __unaligned_cpp
dev_langs: C++
helpviewer_keywords: __unaligned keyword [C++]
ms.assetid: 0cd83aad-1840-47e3-ad33-59bfcbe6375b
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: da662cf9cbe17539381766d37255e63d958fb7b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="unaligned"></a>__unaligned
포인터를 `__unaligned` 한정자로 선언하는 경우, 컴파일러는 포인터가 정렬되지 않은 데이터의 주소 지정한다고 가정합니다. 따라서 IPF(Itanium Processor Family) 컴퓨터를 대상으로 하는 응용 프로그램의 경우, 컴파일러는 정렬되지 않은 데이터를 한 번에 1바이트씩 읽는 코드를 생성합니다.  
  
## <a name="remarks"></a>설명  
 `__unaligned` 한정자를 사용할 수는 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 및 [!INCLUDE[vcpritanium](../cpp/includes/vcpritanium_md.md)] 컴파일러 하지만 IPF 컴퓨터를 대상으로 하는 영향을 줌만 응용 프로그램입니다. 이 한정자는 주소가 지정된 데이터의 정렬만을 설명하며, 포인터 자체는 정렬된 것으로 가정합니다.  
  
 [!INCLUDE[vcpritanium](../cpp/includes/vcpritanium_md.md)] 프로세서가 정렬이 잘못 된 데이터에 액세스 하 고 오류를 처리 하는 시간으로 인해 성능이 저하 때 정렬 오류가 발생 합니다. `__unaligned` 한정자를 사용해 프로세서가 데이터를 한 번에 1 바이트씩 읽도록 하여 오류를 방지합니다. 이 한정자에 대 한 필요 하지 않습니다. [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 응용 프로그램 때문에 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 프로세서에서 오류 없이 정렬이 잘못 된 데이터를 처리 합니다.  
  
 정렬에 대한 자세한 내용은 다음을 참조하십시오.  
  
-   [align](../cpp/align-cpp.md)  
  
-   [__alignof 연산자](../cpp/alignof-operator.md)  
  
-   [pack](../preprocessor/pack.md)  
  
-   [/Zp (구조체 멤버 맞춤)](../build/reference/zp-struct-member-alignment.md)  
  
-   [구조체 맞춤 예제](../build/examples-of-structure-alignment.md)  
  
## <a name="example"></a>예  
  
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
  
## <a name="see-also"></a>참고 항목  
 [키워드](../cpp/keywords-cpp.md)