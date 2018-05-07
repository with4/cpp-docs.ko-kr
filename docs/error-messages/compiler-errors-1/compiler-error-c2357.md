---
title: 컴파일러 오류 C2357 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2357
dev_langs:
- C++
helpviewer_keywords:
- C2357
ms.assetid: d1083945-0ea2-4385-9e66-8c665978806c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c8739576eced6b831f5c3b72d85417e2daabb06
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2357"></a>컴파일러 오류 C2357
'identifier': 'type' 형식의 함수를 이어야 합니다  
  
 버전을 선언 하는 코드는 `atexit` 버전이 일치 하지 않는 함수는 컴파일러에서 내부적으로 선언 합니다. 선언 `atexit` 다음과 같습니다.  
  
```  
int __cdecl atexit(void (__cdecl *)());  
```  
  
 자세한 내용은 참조 [init_seg](../../preprocessor/init-seg.md)합니다.  
  
 다음 샘플에서는 C2357 오류가 생성 됩니다.  
  
```  
// C2357.cpp  
// compile with: /c  
// C2357 expected  
#pragma warning(disable : 4075)  
// Uncomment the following line to resolve.  
// int __cdecl myexit(void (__cdecl *)());  
#pragma init_seg(".mine$m",myexit)  
```