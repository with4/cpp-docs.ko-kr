---
title: "컴파일러 경고 (수준 1) C4228 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4228
dev_langs: C++
helpviewer_keywords: C4228
ms.assetid: 9301d660-d601-464e-83f5-7ed844a3c6dc
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5e924a89b6da03f9ae14baabb222a7baa87dd120
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4228"></a>컴파일러 경고(수준 1) C4228
비표준 확장이 사용 됨: 선언 자 목록에서 쉼표 뒤의 한정자는 무시 됩니다.  
  
 한정자를 사용 하 여 같은 **const** 또는 `volatile` 후 변수를 선언할 때 쉼표는 Microsoft 확장 ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).  
  
## <a name="example"></a>예  
  
```  
// C4228.cpp  
// compile with: /W1  
int j, const i = 0;  // C4228  
int k;  
int const m = 0;  // ok  
int main()  
{  
}  
```