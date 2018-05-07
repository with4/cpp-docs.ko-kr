---
title: 컴파일러 오류 C3808 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3808
dev_langs:
- C++
helpviewer_keywords:
- C3808
ms.assetid: 2ee8ac97-3ea4-417a-8710-be73a7f98cf4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d645760a15a82f502c82f4c0d0310f7826e70e45
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3808"></a>컴파일러 오류 C3808
'type': ComImport 특성이 있는 클래스에는 'member' 멤버를 추상만 정의할 수 없습니다 또는 dllimport 함수를 사용할 수 있습니다.  
  
 파생 된 형식은 <xref:System.Runtime.InteropServices.ComImportAttribute> 정의할 수 없습니다. `member`합니다.  
  
 **/clr:pure** 및 **/clr:safe** 컴파일러 옵션은 Visual Studio 2015에서는 더 이상 사용되지 않습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3808 오류가 발생 합니다.  
  
```  
// C3808.cpp  
// compile with: /c /clr:pure user32.lib  
using namespace System::Runtime::InteropServices;  
  
[System::Runtime::InteropServices::ComImportAttribute()]  
ref struct S1 {  
   int f() {}   // C3808  
   virtual int g() abstract;   // OK  
  
   [DllImport("msvcrt.dll")]  
   int printf(System::String ^, int i);   // OK  
};  
```