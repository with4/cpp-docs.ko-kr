---
title: "컴파일러 경고 (수준 4) C4400 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4400
dev_langs: C++
helpviewer_keywords: C4400
ms.assetid: f135fe98-4f92-4e07-9d71-2621b36ee755
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 615a315ff2d9ff3f517c0b046317400792760b73
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4400"></a>컴파일러 경고(수준 4) C4400
'type':이 형식에 대해 const/volatile 한정자는 지원 되지 않습니다  
  
 [const](../../cpp/const-cpp.md)및 [휘발성](../../cpp/volatile-cpp.md)한정자의 공용 언어 런타임 형식 변수와 함께 작동 하지 것입니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C4400 오류가 발생 합니다.  
  
```  
// C4400.cpp  
// compile with: /clr /W4  
// C4401 expected  
using namespace System;  
#pragma warning (disable : 4101)  
int main() {  
   const String^ str;   // C4400  
   volatile String^ str2;   // C4400  
}  
```