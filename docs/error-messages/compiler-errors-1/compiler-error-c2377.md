---
title: "컴파일러 오류 C2377 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2377
dev_langs:
- C++
helpviewer_keywords:
- C2377
ms.assetid: f7660965-bf4c-4cd9-8307-1bd7016678a1
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: df5596f92c0205a45f3ef03e2ffba212bf168c30
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2377"></a>컴파일러 오류 C2377
'identifier': 재정의. 다른 기호를 사용하여 형식 정의를 오버로드할 수 없습니다.  
  
 `typedef` 식별자가 다시 정의되었습니다.  
  
 다음 샘플에서는 C2377을 생성합니다.  
  
```  
// C2377.cpp  
// compile with: /c  
typedef int i;  
int i;   // C2377  
int j;   // OK  
```
