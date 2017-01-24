---
title: "방법: out 매개 변수 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "함수 매개 변수"
  - "out 매개 변수"
ms.assetid: 02862448-603c-4e9d-a5c5-b45fe38446e3
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: out 매개 변수 지정
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 샘플에서는 함수 매개 변수를 out 매개 변수로 지정하는 방법과 이 함수를 C\# 프로그램에서 호출하는 방법을 보여 줍니다.  
  
 Visual C\+\+에서는 out 매개 변수를 <xref:System.Runtime.InteropServices.OutAttribute>로 지정합니다.  
  
## 예제  
 이 샘플의 첫 번째 부분은 out 매개 변수를 사용하는 함수를 포함하는 형식이 있는 Visual C\+\+ DLL입니다.  
  
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
  
## 예제  
 다음은 위 예제에서 만든 Visual C\+\+ 구성 요소를 사용하는 C\# 클라이언트입니다.  
  
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
  
  **문자열**   
## 참고 항목  
 [C\+\+ Interop 사용\(암시적 PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)