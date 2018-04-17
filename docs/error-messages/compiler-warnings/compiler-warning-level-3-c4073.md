---
title: 컴파일러 경고 (수준 3) C4073 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C4073
dev_langs:
- C++
helpviewer_keywords:
- C4073
ms.assetid: 50081a6e-6acd-45ff-8484-9b1ea926cc5c
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e30c8439ed146658b3d1fcf258d3b13c37f3dd10
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4073"></a>컴파일러 경고 (수준 3) C4073
이니셜라이저가 라이브러리 초기화 영역  
  
 타사 라이브러리 개발자가 하 여 지정한 라이브러리 초기화 영역을 사용 해야 하는 전용 [#pragma init_seg](../../preprocessor/init-seg.md)합니다. 다음 샘플에서는 C4073 오류가 생성 됩니다.  
  
```  
// C4073.cpp  
// compile with: /W3  
#pragma init_seg(lib)   // C4073  
  
// try this line to resolve the warning  
// #pragma init_seg(user)  
  
int main() {  
}  
```