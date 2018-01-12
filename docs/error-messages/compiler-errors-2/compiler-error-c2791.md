---
title: "컴파일러 오류 C2791 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2791
dev_langs: C++
helpviewer_keywords: C2791
ms.assetid: 938ad1fb-75d9-4ce2-ad92-83d6249005b5
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 12f3377ae2c8b1de572c9a498a99fae3236274c3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2791"></a>컴파일러 오류 C2791
'super'를 잘못 사용 했습니다: 'class' 기본 클래스가 없습니다  
  
 키워드 [super](../../cpp/super.md) 의 기본 클래스를 사용 하지 않는 클래스 멤버 함수의 컨텍스트 내에서 사용 되었습니다.  
  
 다음 샘플에서는 C2791 오류가 생성 됩니다.  
  
```  
// C2791.cpp  
struct D {  
   void mf() {  
      __super::mf();   // C2791  
   }  
};  
```