---
title: "컴파일러 오류 C3247 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3247
dev_langs:
- C++
helpviewer_keywords:
- C3247
ms.assetid: f9a2bbb5-3fce-40bf-9fd3-835a5f164dbb
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: fc07da3d6fa994bfba9588b1169287da8c0d738b
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3247"></a>컴파일러 오류 C3247
'class1': coclass는 다른 coclass 'class2'에서 상속할 수 없습니다.  
  
 [coclass](../../windows/coclass.md) 특성으로 표시된 클래스는 `coclass` 특성으로 표시된 다른 클래스에서 상속할 수 없습니다.  
  
 다음 샘플에서는 C3247을 생성합니다.  
  
```  
// C3247.cpp  
[module(name="MyLib")];  
[coclass]  
class a {  
};  
  
[coclass]  
class b : public a {   // C3247  
};  
int main() {  
}  
```
