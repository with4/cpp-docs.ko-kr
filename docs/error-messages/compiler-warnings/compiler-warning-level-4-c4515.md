---
title: 컴파일러 경고 (수준 4) C4515 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4515
dev_langs:
- C++
helpviewer_keywords:
- C4515
ms.assetid: 167b5177-3f89-418b-b6c8-7de634f6b28f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 42bdf6edbd55f533a01c5c430ed328ded7e71dde
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33291462"
---
# <a name="compiler-warning-level-4-c4515"></a>컴파일러 경고(수준 4) C4515
'namespace': 네임 스페이스 자체를 사용 합니다.  
  
 네임 스페이스를 재귀적으로 사용된 합니다.  
  
 다음 샘플에서는 C4515 오류가 생성 됩니다.  
  
```  
// C4515.cpp  
// compile with: /W4  
namespace A  
{  
   using namespace A; // C4515  
}  
  
int main()  
{  
}  
```