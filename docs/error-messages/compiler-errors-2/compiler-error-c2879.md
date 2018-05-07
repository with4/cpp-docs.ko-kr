---
title: 컴파일러 오류 C2879 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2879
dev_langs:
- C++
helpviewer_keywords:
- C2879
ms.assetid: ac92b645-2394-49de-8632-43d44e0553ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ba1738da7d349ecafd9f10f31d8f05ac1f12df0a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
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