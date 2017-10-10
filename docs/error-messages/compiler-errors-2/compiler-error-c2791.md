---
title: "컴파일러 오류 C2791 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2791
dev_langs:
- C++
helpviewer_keywords:
- C2791
ms.assetid: 938ad1fb-75d9-4ce2-ad92-83d6249005b5
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 894f0fb735e4fea7d590eb53401243c0d8581c49
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

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
