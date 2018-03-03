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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4de37b504d32eabbd97dcb2f4fbbafc82841f713
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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