---
title: "컴파일러 오류 C2005 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2005
dev_langs:
- C++
helpviewer_keywords:
- C2005
ms.assetid: 090530ed-e0ec-4358-833a-ca24260e7ffe
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d2cd2437b7a8a6ea9e5897fddb0af80be46ec7dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2005"></a>컴파일러 오류 C2005
\#선 하는데 'token'는 줄 번호가 있어야 하는데  
  
 `#line` 지시문 다음에 줄 번호와 야 합니다.  
  
 다음 샘플에서는 C2005 오류가 생성 됩니다.  
  
```  
// C2005.cpp  
int main() {  
   int i = 0;  
   #line i   // C2005  
}  
```  
  
 해결 방법:  
  
```  
// C2005b.cpp  
int main() {  
   int i = 0;  
   #line 0  
}  
```