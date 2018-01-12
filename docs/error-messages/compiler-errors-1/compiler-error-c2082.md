---
title: "컴파일러 오류 C2082 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2082
dev_langs: C++
helpviewer_keywords: C2082
ms.assetid: 87a6d442-157c-46e8-9bff-8388f8338ae0
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 43336d881e56cc3f02330e0201b4020d8ba15ee5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2082"></a>컴파일러 오류 C2082
'identifier' 정식 매개 변수 재정의  
  
 함수의 정식 매개 변수가 함수 본문 내에서 다시 선언됩니다. 이 오류를 해결하려면 재정의를 제거합니다.  
  
 다음 샘플에서는 C2082를 생성합니다.  
  
```  
// C2082.cpp  
void func(int i) {  
   int i;   // C2082  
   int ii;   // OK  
}  
```