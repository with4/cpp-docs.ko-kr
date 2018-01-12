---
title: "컴파일러 경고 (수준 2) C4094 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4094
dev_langs: C++
helpviewer_keywords: C4094
ms.assetid: e68929fb-3a1c-4be7-920b-d5f79f534f99
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 27b2d664996ee3db1c1b505eb8db0346d683ff8a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-2-c4094"></a>컴파일러 경고 (수준 2) C4094
태그가 지정 되지 않은 ' token' 기호가 없는 선언  
  
 컴파일러는 태그가 지정 되지 않은 구조체, 공용 구조체 또는 클래스를 사용 하 여 빈 선언을 발견 했습니다. 선언이 무시 됩니다.  
  
## <a name="example"></a>예  
  
```  
// C4094.cpp  
// compile with: /W2  
struct  
{  
};   // C4094  
  
int main()  
{  
}  
```  
  
 이 조건은 ANSI 규격 오류를 발생 시킵니다 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).