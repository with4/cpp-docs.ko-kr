---
title: "컴파일러 오류 C2838 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2838
dev_langs:
- C++
helpviewer_keywords:
- C2838
ms.assetid: 176b2ad6-7a84-4019-b97e-328866054457
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 75f6cdae94cd1be386fbe6af2cc492404162d0d7
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2838"></a>컴파일러 오류 C2838
'member': 멤버 선언의 정규화 된 이름이 잘못 되었습니다.  
  
 클래스, 구조체 또는 공용 구조체 정규화 된 이름을 사용 하 여 다른 클래스, 구조체 또는 공용 구조체의 멤버를 다시 선언 합니다.  
  
 다음 샘플에서는 C2838 오류가 생성 됩니다.  
  
```  
// C2838.cpp  
// compile with: /c  
class Bellini {  
public:  
    void Norma();  
};  
  
class Bottesini {  
   Bellini::Norma();  // C2838  
};  
```
