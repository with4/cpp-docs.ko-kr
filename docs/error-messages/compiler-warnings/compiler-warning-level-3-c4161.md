---
title: 컴파일러 경고 (수준 3) C4161 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4161
dev_langs:
- C++
helpviewer_keywords:
- C4161
ms.assetid: 03d3be61-83f1-4009-8310-8758ab67055f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1c81072c5121bea4a323c3eb16cc58c6f28c06f7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4161"></a>컴파일러 경고(수준 3) C4161
\#pragma pragma(pop...): 푸시 횟수 보다 팝  
  
 소스 코드에서 pragma ***pragma***에 대한 팝 횟수가 푸시 횟수보다 하나 더 많으므로 스택이 예상대로 동작하지 않을 수 있습니다. 경고를 방지하려면 팝 횟수가 푸시 횟수를 초과하지 않도록 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 C4161을 생성합니다.  
  
```  
// C4161.cpp  
// compile with: /W3 /LD  
#pragma pack(push, id)  
#pragma pack(pop, id)  
#pragma pack(pop, id)   // C4161, an extra pop  
  
#pragma bss_seg(".my_data1")  
int j;  
  
#pragma bss_seg(push, stack1, ".my_data2")     
int l;  
  
#pragma bss_seg(pop, stack1)  
int m;  
  
#pragma bss_seg(pop, stack1)   // C4161  
```