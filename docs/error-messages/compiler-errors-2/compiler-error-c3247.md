---
title: "컴파일러 오류 C3247 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 09c62f455bc666296222a2079ef6b0b97c507d85
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3247"></a>컴파일러 오류 C3247
'class1': coclass는 다른 coclass 'class2'에서 상속할 수 없습니다.  
  
 클래스에 표시 된 [coclass](../../windows/coclass.md) 특성으로 표시 된 다른 클래스에서 상속할 수 없습니다는 `coclass` 특성입니다.  
  
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
