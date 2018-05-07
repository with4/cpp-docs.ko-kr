---
title: 컴파일러 경고 (수준 4) C4336 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4336
dev_langs:
- C++
helpviewer_keywords:
- C4336
ms.assetid: 93f199dd-d6dd-42c0-82d8-c12d101a7235
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4da5302df9b2072089ce84c349577e1ea8ea236f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4336"></a>컴파일러 경고(수준 4) C4336
상호 참조 된 형식 라이브러리 'type_lib1' 'type_lib2' 가져오기 전에 가져오기  
  
 으로 참조 된 형식 라이브러리는 [#import](../../preprocessor/hash-import-directive-cpp.md) 지시문입니다. 형식 라이브러리와 참조 되지 않은 다른 형식 라이브러리에 대 한 참조를 포함 하는 반면 `#import`합니다. 컴파일러에서이.tlb 파일을 찾았습니다.  
  
 다음 두 파일 (midl.exe를 사용 하 여 컴파일된)에서 만든 디스크에 지정 된 두 개의 형식 라이브러리:  
  
```  
// c4336a.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]  
library c4336aLib  
{  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]  
   enum E_C4336  
   {  
      one, two, three  
   };  
};  
```  
  
 두 번째 형식 라이브러리:  
  
```  
// c4336b.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]  
library C4336bLib  
{  
   importlib ("c4336a.tlb");  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]  
   struct S_C4336  
   {  
      enum E_C4336 e;  
   };  
};  
```  
  
 다음 샘플에서는 C4336 오류가 생성 됩니다.  
  
```  
// C4336.cpp  
// compile with: /W4 /LD  
// #import "C4336a.tlb"  
#import "C4336b.tlb"   // C4336, uncomment previous line to resolve  
```