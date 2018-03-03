---
title: "컴파일러 경고 (수준 3) C4334 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4334
dev_langs:
- C++
helpviewer_keywords:
- C4334
ms.assetid: d845857f-bc95-4faf-a079-626a0cf935ba
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7218caa399aec0bd1b9755fb6d0942991732121e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4334"></a>컴파일러 경고(수준 3) C4334
'operator': 32 비트 시프트의 결과가 암시적으로 64 비트로 변환 (64 비트 시프트를 사용 했습니다.)  
  
 32 비트 시프트의 결과가 64 비트 및 64 비트 시프트 원래 컴파일러에서는 암시적으로 변환 되었습니다.  이 경고를 해결 하려면 64 비트 시프트를 사용 하거나 64 비트를 시프트 결과 명시적으로 캐스팅 하십시오.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C4334 오류가 발생 합니다.  
  
```  
// C4334.cpp  
// compile with: /W3 /c  
void SetBit(unsigned __int64 *p, int i) {  
   *p |= (1 << i);   // C4334  
   *p |= (1i64 << i);   // OK  
}  
```