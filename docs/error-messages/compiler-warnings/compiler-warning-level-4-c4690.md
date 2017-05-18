---
title: "컴파일러 경고 (수준 4) C4690 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4690
dev_langs:
- C++
helpviewer_keywords:
- C4690
ms.assetid: 080a0ea1-458b-477b-a37a-4a34c94709ff
caps.latest.revision: 9
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 8791cb8b8c484dfe085d967eab4469bd47d8cb53
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-4-c4690"></a>컴파일러 경고(수준 4) C4690
[ emitidl( pop ) ]: 데이터를 넣는 작업(push)보다 데이터를 꺼내는 작업(pop)이 많습니다.  
  
 [emitidl](../../windows/emitidl.md) 특성을 넣은 한 번 더 팝 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4690을 생성합니다.  
  
```  
// C4690.cpp  
// compile with: /c /W4  
[emitidl(pop)];   // C4690  
class x {};  
```
