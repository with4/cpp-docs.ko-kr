---
title: 컴파일러 오류 C3368 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3368
dev_langs:
- C++
helpviewer_keywords:
- C3368
ms.assetid: 5bfd5be4-dfa9-4b33-9612-010561b40955
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 438f9a4f23dd7069457a635c0db02b66ff8de1e8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3368"></a>컴파일러 오류 C3368
'function declaration': IDL에 대한 호출 규칙이 잘못되었습니다.  
  
 .idl 파일에서 [__stdcall](../../cpp/stdcall.md) 또는 [__cdecl](../../cpp/cdecl.md) 호출 규칙만 사용할 수 있습니다.  
  
 다음 샘플에서는 C3368을 생성합니다.  
  
```  
// C3368.cpp  
// processor: x86  
[idl_module(name="Name", dllname="Some.dll")];  
  
[idl_module(name="Name")]  
int __fastcall f1();   // C3368  
```