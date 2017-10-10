---
title: "컴파일러 오류 C2867 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2867
dev_langs:
- C++
helpviewer_keywords:
- C2867
ms.assetid: 63be26b2-d9ab-4f3d-a8b7-981ce3e4d6b9
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 34fd8669dc210c15488d31a48ffb32198536965d
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2867"></a>컴파일러 오류 C2867
'identifier': 네임 스페이스가 아닙니다  
  
 A `using` 지시문은 네임 스페이스 이외의 항목에 적용 됩니다.  
  
 다음 샘플에서는 C2867 오류가 생성 됩니다.  
  
```  
// C2867.cpp  
// compile with: /c  
namespace N {  
   class X {};  
}  
using namespace N::X;   // C2867  
```
