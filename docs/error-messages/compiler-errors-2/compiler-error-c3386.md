---
title: 컴파일러 오류 C3386 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3386
dev_langs:
- C++
helpviewer_keywords:
- C3386
ms.assetid: 93fa8c33-0f10-402b-8eec-b0a217a1f8dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d378c92fbeff4e8738450e2e49c42c00bd46a6c6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3386"></a>컴파일러 오류 C3386
'type': __declspec (dllexport) /\__declspec(dllimport) WinRTtype 또는 관리 되는에 적용할 수 없습니다  
  
 `dllimport` 및 [dllexport](../../cpp/dllexport-dllimport.md) `__declspec` 한정자 Windows 런타임 또는 관리 되는 유효 하지 않습니다. 형식입니다.  
  
 다음 샘플에서는 C3386 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C3386.cpp  
// compile with: /clr /c  
ref class __declspec(dllimport) X1 {   // C3386  
// try the following line instead  
// ref class X1 {  
};  
```