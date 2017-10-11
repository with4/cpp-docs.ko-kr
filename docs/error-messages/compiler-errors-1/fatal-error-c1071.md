---
title: "심각한 오류 C1071 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1071
dev_langs:
- C++
helpviewer_keywords:
- C1071
ms.assetid: 489f1786-370e-4ecd-af67-538fe6e5bd4e
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: acd48401d3abc17d994e861bf6fb046450d88ca6
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1071"></a>심각한 오류 C1071
주석에서 예기치 않은 파일의 끝이 나타났습니다.  
  
 컴파일러는 주석을 검사 하는 동안 파일의 끝에 도달 합니다.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면  
  
1.  주석 종결자 (* /).  
  
2.  소스 파일의 마지막 줄에서 주석 다음 줄 바꿈 문자가 없습니다.  
  
 다음 샘플에서는 C1071 오류가 생성 됩니다.  
  
```  
// C1071.cpp  
int main() {  
}  
  
/* this comment is fine */  
/* forgot the closing tag        // C1071  
```
