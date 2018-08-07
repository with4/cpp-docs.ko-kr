---
title: 컴파일러 오류 C2749 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2749
dev_langs:
- C++
helpviewer_keywords:
- C2749
ms.assetid: a81aef36-cdca-4d78-89d5-b72eff2500b2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1738bdcc66e05512932fcd9029484dc55e3fc4a0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33236896"
---
# <a name="compiler-error-c2749"></a>컴파일러 오류 C2749
'type': throw 하거나 catch /clr: safe 사용 하는 관리 되는 클래스에 대 한 핸들 수  
  
 사용 하는 경우 **/clr: safe**, throw 또는 catch 참조 형식만 있습니다.  
  
 자세한 내용은 [/clr(공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2749 오류가 생성 됩니다.  
  
```  
// C2749.cpp  
// compile with: /clr:safe  
ref struct MyStruct {  
public:  
   int i;  
};  
  
int main() {  
   MyStruct ^x = gcnew MyStruct;  
  
   // Delete the following 4 lines to resolve.  
   try {   
      throw (1);   // C2749  
   }  
   catch(int){}  
  
   // OK  
   try {  
      throw (x);  
   }  
   catch(MyStruct ^){}   
}  
```