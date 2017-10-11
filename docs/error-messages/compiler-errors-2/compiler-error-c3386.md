---
title: "컴파일러 오류 C3386 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3386
dev_langs:
- C++
helpviewer_keywords:
- C3386
ms.assetid: 93fa8c33-0f10-402b-8eec-b0a217a1f8dc
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8b912d1d75ae120f993c3641ff2e2b561910b4aa
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

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
