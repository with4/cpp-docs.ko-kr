---
title: "컴파일러 오류 C2032 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2032
dev_langs:
- C++
helpviewer_keywords:
- C2032
ms.assetid: 625d7c83-70b6-42c2-a558-81fbc0026324
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 87703c289dc522f62c29fd2110e969fd44abf645
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2032"></a>컴파일러 오류 C2032
'identifier': 함수는 'structorunion' 구조체/공용 구조체의 멤버일 수 없습니다  
  
 구조체 또는 공용 구조체에는 3. 있지만 c + +에 허용 되는 멤버 함수 이 오류를 해결 하려면 c + + 프로그램 컴파일 또는 멤버 함수를 제거 합니다.  
  
 다음 샘플에서는 C2032 오류가 생성 됩니다.  
  
```  
// C2032.c  
struct z {  
   int i;  
   void func();   // C2032  
};  
```  
  
 해결 방법:  
  
```  
// C2032b.c  
// compile with: /c  
struct z {  
   int i;  
};  
```