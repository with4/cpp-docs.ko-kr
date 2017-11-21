---
title: "방법: MSIL에서 Throw 되는 네이티브 코드에서 예외를 Catch | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- exceptions, catching
- catching exceptions, thrown from MSIL
- MSIL, catching exceptions in native code
ms.assetid: c15afd2b-8505-43bf-8a4a-f1d41532a124
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: dbb17c9ed16f771f60054bcde1f8ea5145047c35
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-catch-exceptions-in-native-code-thrown-from-msil"></a>방법: 네이티브 코드에서 MSIL이 throw한 예외 catch
네이티브 코드에서 MSIL에서 네이티브 c + + 예외를 catch 할 수 있습니다.  와 CLR 예외를 catch 할 수 있습니다 `__try` 및 `__except`합니다.  
  
 자세한 내용은 참조 [구조적 예외 처리 (C/c + +)](../cpp/structured-exception-handling-c-cpp.md) 및 [c + + 예외 처리](../cpp/cpp-exception-handling.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플 MSIL 예외를 throw 하는 두 함수는 네이티브 예외를 throw 하 고 다른을 사용 하 여 모듈을 정의 합니다.  
  
```  
// catch_MSIL_in_native.cpp  
// compile with: /clr /c  
void Test() {  
   throw ("error");  
}  
  
void Test2() {  
   throw (gcnew System::Exception("error2"));  
}  
```  
  
## <a name="example"></a>예제  
 다음 샘플 네이티브와 MSIL 예외를 catch 하는 모듈을 정의 합니다.  
  
```  
// catch_MSIL_in_native_2.cpp  
// compile with: /clr catch_MSIL_in_native.obj  
#include <iostream>  
using namespace std;  
void Test();  
void Test2();  
  
void Func() {  
   // catch any exception from MSIL  
   // should not catch Visual C++ exceptions like this  
   // runtime may not destroy the object thrown  
   __try {  
      Test2();  
   }  
   __except(1) {  
      cout << "caught an exception" << endl;  
   }  
  
}  
  
int main() {  
   // catch native C++ exception from MSIL  
   try {  
      Test();  
   }  
   catch(char * S) {  
      cout << S << endl;  
   }  
   Func();  
}  
```  
  
```Output  
error  
caught an exception  
```  
  
## <a name="see-also"></a>참고 항목  
 [예외 처리](../windows/exception-handling-cpp-component-extensions.md)