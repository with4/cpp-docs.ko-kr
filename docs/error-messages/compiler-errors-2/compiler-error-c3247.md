---
title: 컴파일러 오류 C3247 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3247
dev_langs:
- C++
helpviewer_keywords:
- C3247
ms.assetid: f9a2bbb5-3fce-40bf-9fd3-835a5f164dbb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d64ba734203cdac6a56a82f3fd44853d62af53fd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33249257"
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