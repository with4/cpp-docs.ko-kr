---
title: '방법: 지정 out 매개 변수 | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- function parameters
- out parameters
ms.assetid: 02862448-603c-4e9d-a5c5-b45fe38446e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: adc56a65829064376d2472206f916d32d369cb01
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-specify-an-out-parameter"></a>방법: out 매개 변수 지정
이 샘플에서는 C# 프로그램에서 함수를 호출 하는 방법과 함수 매개 변수는 out 매개 변수를 지정 하는 방법을 보여 줍니다.  
  
 Visual c + +에는 out 매개 변수가 지정 된 <xref:System.Runtime.InteropServices.OutAttribute> 합니다.  
  
## <a name="example"></a>예제  
 이 샘플의 첫 번째 부분은 out 매개 변수를 사용 하는 함수를 포함 하는 형식과 Visual c + + DLL입니다.  
  
```  
// cpp_out_param.cpp  
// compile with: /LD /clr:safe  
using namespace System;  
public value struct TestStruct {  
   static void Test([Runtime::InteropServices::Out] String^ %s) {  
      s = "a string";  
   }  
};  
```  
  
## <a name="example"></a>예제  
 이전 예제에서 만든 Visual c + + 구성 요소를 사용 하는 C# 클라이언트입니다.  
  
```  
// cpp_out_param_2.cs  
// compile with: /reference:cpp_out_param.dll  
using System;  
class TestClass {  
   public static void Main() {  
      String t;  
      TestStruct.Test(out t);  
      System.Console.WriteLine(t);  
   }  
}  
```  
  
```Output  
a string  
```  
  
## <a name="see-also"></a>참고 항목  
 [C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)