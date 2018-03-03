---
title: "컴파일러 경고 (수준 1) C4600 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4600
dev_langs:
- C++
helpviewer_keywords:
- C4600
ms.assetid: f023a2a1-7fc4-463f-a434-dc93fcd3f4e9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b031f423d2230ffea03c33d35c3d959cafc9bf37
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4600"></a>컴파일러 경고(수준 1) C4600
\#pragma '매크로 name': 유효한 비어 있지 않은 문자열이 필요 합니다.  
  
 강제 또는 매크로 이름을 사용 하 여 팝 하는 경우 빈 문자열을 지정할 수 없습니다는 [pop_macro](../../preprocessor/pop-macro.md) 또는 [push_macro](../../preprocessor/push-macro.md)합니다.  
  
 다음 샘플에서는 C4600 오류가 생성 됩니다.  
  
```  
// C4600.cpp  
// compile with: /W1  
int main()  
{  
   #pragma push_macro("")   // C4600 passing an empty string  
}  
```