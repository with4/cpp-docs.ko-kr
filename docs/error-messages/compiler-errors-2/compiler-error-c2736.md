---
title: "컴파일러 오류 C2736 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2736
dev_langs:
- C++
helpviewer_keywords:
- C2736
ms.assetid: 95a6bc28-c0cb-49dc-87e6-e993dbbba881
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 303ca2ead2411bcc0ceb24ee1329094de2adbb8a
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2736"></a>컴파일러 오류 C2736
캐스트에는 'keyword' 키워드를 사용할 수 없습니다.  
  
 키워드는 캐스트에 사용할 수 없습니다.  
  
 다음 샘플에서는 C2736 오류가 생성 됩니다.  
  
```  
// C2736.cpp  
int main() {  
   return (virtual) 0;   // C2736  
   // try the following line instead  
   // return 0;  
}  
```
