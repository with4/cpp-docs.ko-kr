---
title: 심각한 오류 C1071 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1071
dev_langs:
- C++
helpviewer_keywords:
- C1071
ms.assetid: 489f1786-370e-4ecd-af67-538fe6e5bd4e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e9cef64c327c0fd3b668947de52f2776cca2833c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33227197"
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