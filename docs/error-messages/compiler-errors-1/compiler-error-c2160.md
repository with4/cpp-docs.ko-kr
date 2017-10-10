---
title: "컴파일러 오류 C2160 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2160
dev_langs:
- C++
helpviewer_keywords:
- C2160
ms.assetid: a1f694a7-fb16-4437-b7f5-a1af6da94bc5
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: caef1127e06bbf0b12480b2c10239c77ae6c0ad5
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2160"></a>컴파일러 오류 C2160
매크로 정의 시작에 '##'이 올 수 없습니다.  
  
 매크로 정의가 토큰 붙여넣기 연산자(##)로 시작되었습니다.  
  
 다음 샘플에서는 C2160을 생성합니다.  
  
```  
// C2160.cpp  
// compile with: /c  
#define mac(a,b) #a   // OK  
#define mac(a,b) ##a   // C2160  
```
