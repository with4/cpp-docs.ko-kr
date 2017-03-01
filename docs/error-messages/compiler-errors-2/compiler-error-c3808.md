---
title: "컴파일러 오류 C3808 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3808
dev_langs:
- C++
helpviewer_keywords:
- C3808
ms.assetid: 2ee8ac97-3ea4-417a-8710-be73a7f98cf4
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 989f17e8f59afc6a04ed4101204053fc971c6a62
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3808"></a>컴파일러 오류 C3808
'type': dllimport 함수를 사용할 수 또는 ComImport 특성으로 클래스에는 'member' 멤버를 추상만 정의할 수 없습니다  
  
 파생 된 형식은 <xref:System.Runtime.InteropServices.ComImportAttribute>정의할 수 없습니다. `member`.</xref:System.Runtime.InteropServices.ComImportAttribute>  
  
 **/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서는 사용 되지 않습니다.  
  
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
