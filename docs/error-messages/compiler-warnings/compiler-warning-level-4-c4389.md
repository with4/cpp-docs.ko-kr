---
title: "컴파일러 경고 (수준 4) C4389 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: c4389
dev_langs: C++
helpviewer_keywords: C4389
ms.assetid: fc0e3a8e-f766-437c-b7f1-e61abb2a8765
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3d26260dd3e57c9677cd934605b609577028c7e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4389"></a>컴파일러 경고(수준 4) C4389
'operator': signed 또는 unsigned 일치 하지 않습니다.  
  
 작업 서명 되 고 서명 되지 않은 변수를 포함 합니다. 이 인해 데이터가 손실 될 수 있습니다.  
  
 다음 샘플에서는 C4389 오류가 생성 됩니다.  
  
```  
// C4389.cpp  
// compile with: /W4  
#pragma warning(default: 4389)  
  
int main()  
{  
   int a = 9;  
   unsigned int b = 10;  
   if (a == b)   // C4389  
      return 0;  
   else  
      return 0;  
};  
```