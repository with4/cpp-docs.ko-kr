---
title: "컴파일러 오류 C2377 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2377
dev_langs: C++
helpviewer_keywords: C2377
ms.assetid: f7660965-bf4c-4cd9-8307-1bd7016678a1
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6928b3bd4acc0a60804ec14374bd2e28b4348e67
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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