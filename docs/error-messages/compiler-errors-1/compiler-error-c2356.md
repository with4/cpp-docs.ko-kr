---
title: "컴파일러 오류 C2356 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2356
dev_langs:
- C++
helpviewer_keywords:
- C2356
ms.assetid: 84d5a816-9a61-4d45-9978-38e485bbf767
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a09e44133b6bea0f79df020b359719cf1a1754c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2356"></a>컴파일러 오류 C2356
초기화 세그먼트는 변환 단위 동안 바뀌지 않아야 합니다.  
  
 가능한 원인:  
  
-   `#pragma init_seg`앞에 초기화 코드 세그먼트  
  
-   `#pragma init_seg`앞에 다른`#pragma init_seg`  
  
 를 해결 하려면 세그먼트 초기화 코드를 모듈의 시작 부분으로 이동 합니다. 여러 영역을 초기화 해야 하는 경우 별개의 모듈로 옮기십시오.  
  
 다음 샘플에서는 C2356 오류가 생성 됩니다.  
  
```  
// C2356.cpp  
#pragma warning(disable : 4075)  
  
int __cdecl myexit(void (__cdecl *)());  
int __cdecl myexit2(void (__cdecl *)());  
  
#pragma init_seg(".mine$m",myexit)  
#pragma init_seg(".mine$m",myexit2)   // C2356  
```