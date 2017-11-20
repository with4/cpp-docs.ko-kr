---
title: "컴파일러 오류 C2256 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2256
dev_langs: C++
helpviewer_keywords: C2256
ms.assetid: 171fa2bc-8c72-49cd-afe5-d723b7acd3c5
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 54802178136f02d0b334203ebcedf020942f0ed9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2256"></a>컴파일러 오류 C2256
'function'에 friend 지정자를 잘못 사용 했습니다.  
  
 소멸자 또는 생성자로 지정할 수 없습니다는 [friend](../../cpp/friend-cpp.md)합니다.  
  
 다음 샘플에서는 C2256 오류가 생성 됩니다.  
  
```  
// C2256.cpp  
// compile with: /c  
class C {  
public:  
   friend ~C();   // C2256  
   ~C();   // OK  
};  
```