---
title: "컴파일러 경고 (수준 1) C4230 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4230
dev_langs: C++
helpviewer_keywords: C4230
ms.assetid: a4be8729-74b6-44df-a5ea-e3f45aad0f8f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c50738e464452599ae8d20eaa3266b75fe301934
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4230"></a>컴파일러 경고(수준 1) C4230
사용 하는 오래 된 구문: 오래; 한정자가 무시 되었습니다  
  
 와 같은 Microsoft 한정자 전에 한정자를 사용 하 여 `__cdecl` 쿼리로 됩니다.  
  
## <a name="example"></a>예  
  
```  
// C4230.cpp  
// compile with: /W1 /LD  
int __cdecl const function1();   // C4230 const ignored  
```