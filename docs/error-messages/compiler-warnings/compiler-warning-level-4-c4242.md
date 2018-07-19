---
title: 컴파일러 경고 (수준 4) C4242 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4242
dev_langs:
- C++
helpviewer_keywords:
- C4242
ms.assetid: 8df742e1-fbf1-42f3-8e93-c0e1c222dc7e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: befe02b363c17a670d3b33632ffa50ed8a7cb1f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33294484"
---
# <a name="compiler-warning-level-4-c4242"></a>컴파일러 경고(수준 4) C4242
'identifier': 'type1'에서 'type2', 데이터가 손실 될 수로 변환  
  
 형식이 서로 다릅니다. 형식 변환의 데이터가 손실에서 될 수 있습니다. 컴파일러에서 형식 변환 합니다.  
  
 기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 를 참조하세요.  
  
 C4242 대 한 추가 정보를 참조 하십시오. [일반적인 컴파일러 오류](http://msdn.microsoft.com/library/windows/desktop/aa384160)합니다.  
  
 다음 샘플에서는 c 4242 오류가 생성 됩니다.  
  
```  
// C4242.cpp  
// compile with: /W4  
#pragma warning(4:4242)  
int func() {  
   return 0;  
}  
  
int main() {  
   char a;  
   a = func();   // C4242, return type and variable type do not match  
}  
```