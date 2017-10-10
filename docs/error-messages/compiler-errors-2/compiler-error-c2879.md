---
title: "컴파일러 오류 C2879 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2879
dev_langs:
- C++
helpviewer_keywords:
- C2879
ms.assetid: ac92b645-2394-49de-8632-43d44e0553ed
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 4bb972ffa8bee016dd158490d123353bd6f46a8e
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2879"></a>컴파일러 오류 C2879
'symbol':만 기존 네임 스페이스 별칭 정의 네임 스페이스로 대체 이름을 지정할 수 있습니다  
  
 만들 수 없습니다는 [네임 스페이스 별칭](../../cpp/namespaces-cpp.md#namespace_aliases) 네임 스페이스 이외의 기호를 합니다.  
  
 다음 샘플에서는 C2879 오류가 생성 됩니다.  
  
```  
// C2879.cpp  
int main() {  
   int i;  
   namespace A = i;   // C2879 i is not a namespace  
}  
```
