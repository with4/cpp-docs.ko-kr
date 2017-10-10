---
title: "컴파일러 오류 C2378 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2378
dev_langs:
- C++
helpviewer_keywords:
- C2378
ms.assetid: 507a91c6-ca72-48df-b3a4-2cf931c86806
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 279a6c8c5de43f6ac0a9438e06f93b5d3b4294b9
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2378"></a>컴파일러 오류 C2378
'identifier': 재정의. 형식 정의를 사용하여 기호를 오버로드할 수 없습니다.  
  
 식별자가 `typedef`로 다시 정의되었습니다.  
  
 다음 샘플에서는 C2378을 생성합니다.  
  
```  
// C2378.cpp  
// compile with: /c  
int i;  
typedef int i;   // C2378  
typedef int b;   // OK  
```
