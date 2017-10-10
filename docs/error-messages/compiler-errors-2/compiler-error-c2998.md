---
title: "컴파일러 오류 C2998 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2998
dev_langs:
- C++
helpviewer_keywords:
- C2998
ms.assetid: 8193d491-b5d9-4477-acb1-cf166889c070
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 64a1bf4d496e31f5d189b315180a6bd60d4bc867
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2998"></a>컴파일러 오류 C2998
'identifier': 템플릿 정의일 수 없습니다.  
  
 컴파일러에서 템플릿 정의에 사용되는 구문을 처리할 수 없습니다.  
  
 다음 샘플에서는 C2998을 생성합니다.  
  
```  
// C2998.cpp  
// compile with: /c  
template <class T> int x = 1018; // C2998  
```
