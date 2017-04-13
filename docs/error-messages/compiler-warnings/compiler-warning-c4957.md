---
title: "컴파일러 경고 C4957 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4957
dev_langs:
- C++
helpviewer_keywords:
- C4957
ms.assetid: a18c52d4-23e2-44f1-b4b5-f7fa5a7f3987
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 8eb7283942a8a89fc3322983c41c68082b6c5cee
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-c4957"></a>컴파일러 경고 C4957
'cast': 'cast_from'에서 'cast_to'로의 명시적 캐스트는 확인할 수 없습니다.  
  
 캐스트로 인해 확인할 수 없는 이미지가 발생합니다.  
  
 일부 캐스트는 안전합니다(예: 사용자 정의 변환을 트리거하는 `static_cast` 및 `const_cast`). A [safe_cast](../../windows/safe-cast-cpp-component-extensions.md) 안정형 코드를 생성 하도록 보장 됩니다.  
  
 자세한 내용은 참조 [순수형 및 안정형 코드 (C + + /cli CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md)합니다.  
  
 이 경고는 오류로 발생 하며를 비활성화할 수 있습니다는 [경고](../../preprocessor/warning.md) pragma 또는 [/wd](../../build/reference/compiler-option-warning-level.md) 컴파일러 옵션입니다.  
  
 다음 샘플에서는 C4957을 생성합니다.  
  
```  
// C4957.cpp  
// compile with: /clr:safe  
// #pragma warning( disable : 4957 )  
using namespace System;  
int main() {  
   Object ^ o = "Hello, World!";  
   String ^ s = static_cast<String^>(o);   // C4957  
   String ^ s2 = safe_cast<String^>(o);   // OK  
}  
```
