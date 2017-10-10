---
title: "컴파일러 오류 C2457 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2457
dev_langs:
- C++
helpviewer_keywords:
- C2457
ms.assetid: 347e169d-23ad-434f-8836-5b09b53980ff
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: fd5d73850839c73ea6260165151415115251a59e
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2457"></a>컴파일러 오류 C2457
'매크로': 미리 정의 된 매크로 함수 본문 외부에 사용할 수 없습니다  
  
 와 같은 미리 정의 된 매크로 사용 하려고 했습니다. [__FUNCTION\_\_](../../preprocessor/predefined-macros.md), 전역 공간에서 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2457 오류가 생성 됩니다.  
  
```  
// C2457.cpp  
#include <stdio.h>  
  
__FUNCTION__;   // C2457, cannot be global  
  
int main()   
{  
    printf_s("\n%s",__FUNCTION__);   // OK  
}  
```
