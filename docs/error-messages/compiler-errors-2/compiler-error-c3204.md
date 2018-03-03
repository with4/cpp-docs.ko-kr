---
title: "컴파일러 오류 C3204 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3204
dev_langs:
- C++
helpviewer_keywords:
- C3204
ms.assetid: 06e578da-0262-48c8-b2ae-be1cd6d28884
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 88ee07c8319e3b8c28eaca0b7295ef1ce6e06d00
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3204"></a>컴파일러 오류 C3204
'_alloca'는 catch 블록 내부에서 호출할 수 없습니다.  
  
 이 오류는 catch 블록 내에서 [_alloca](../../c-runtime-library/reference/alloca.md) 호출을 사용하는 경우에 발생합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3204를 생성합니다.  
  
```  
// C3204.cpp  
// compile with: /EHsc  
#include <malloc.h>  
  
void ShowError(void)  
{  
   try  
   {  
   }  
   catch(...)  
   {  
      _alloca(1);   // C3204  
   }  
}  
```