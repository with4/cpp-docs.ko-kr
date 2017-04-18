---
title: "컴파일러 경고 (수준 1) C4794 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4794
dev_langs:
- C++
helpviewer_keywords:
- C4794
ms.assetid: badc9c36-fa1a-4fec-929b-7bfda7a7b79f
caps.latest.revision: 11
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
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 8f73e3da504960f737f175fff4c9d7b07084833a
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4794"></a>컴파일러 경고(수준 1) C4794
스레드 로컬 저장소 변수 'variable'의 세그먼트가 'section name'에서 '.tls$'로 변경되었습니다.  
  
 사용한 [#pragma data_seg](../../preprocessor/data-seg.md) .tls $로 시작 하지 않는 섹션에 tls 변수를 추가할입니다.  
  
 .Tls$*x* 섹션은 개체 파일에 존재 여기서 [__declspec (thread)](../../cpp/thread.md) 변수 정의 됩니다. EXE 또는 DLL의 .tls 섹션은 다음 섹션에서 발생합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4794를 생성합니다.  
  
```  
// C4794.cpp  
// compile with: /W1 /c  
#pragma data_seg(".someseg")  
__declspec(thread) int i;   // C4794  
  
// OK  
#pragma data_seg(".tls$9")  
__declspec(thread) int j;  
```
