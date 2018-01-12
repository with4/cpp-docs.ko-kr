---
title: "컴파일러 오류 C2075 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2075
dev_langs: C++
helpviewer_keywords: C2075
ms.assetid: 8b1865d2-540b-4117-b982-e7a58a0b6cf7
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 375c2c7d422ed15f127b37b2f88f44c215f0962d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2075"></a>컴파일러 오류 C2075
'identifier': 배열 초기화에는 중괄호가 있어야 합니다.  
  
 지정된 배열 이니셜라이저 주변에 중괄호가 없습니다.  
  
 다음 샘플에서는 C2075를 생성합니다.  
  
```  
// C2075.c  
int main() {  
   int i[] = 1, 2, 3 };   // C2075  
}  
```  
  
 해결 방법:  
  
```  
// C2075b.c  
int main() {  
   int j[] = { 1, 2, 3 };  
}  
```