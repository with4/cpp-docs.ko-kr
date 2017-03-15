---
title: "컴파일러 오류 C3246 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
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
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: ac8458487d9ed500420f2e687f8eb7c37bf053da
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3246"></a>컴파일러 오류 C3246
'class': 'sealed'로 선언했으므로 'type'에서 상속할 수 없습니다.  
  
로 표시 된 클래스 [봉인](../../windows/sealed-cpp-component-extensions.md) 다른 클래스에 대 한 기본 클래스를 사용할 수 없습니다.  
  
다음 샘플에서는 C3246을 생성합니다.  
  
```  
// C3246_2.cpp  
// compile with: /clr /LD  
ref class X sealed {};  
  
ref class Y : public X {}; // C3246  
```  

