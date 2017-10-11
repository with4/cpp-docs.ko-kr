---
title: "컴파일러 오류 C3246 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3246
dev_langs:
- C++
helpviewer_keywords:
- C3246
ms.assetid: ad85224a-e540-479b-a5eb-a3bc3964c30b
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 262dc8bde5dcb4c12909c69bce3fa867685245eb
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3246"></a>컴파일러 오류 C3246
'class': 'sealed'로 선언했으므로 'type'에서 상속할 수 없습니다.  
  
[sealed](../../windows/sealed-cpp-component-extensions.md) 로 표시된 클래스는 다른 클래스의 기본 클래스일 수 없습니다.  
  
다음 샘플에서는 C3246을 생성합니다.  
  
```  
// C3246_2.cpp  
// compile with: /clr /LD  
ref class X sealed {};  
  
ref class Y : public X {}; // C3246  
```  

