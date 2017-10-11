---
title: "컴파일러 오류 C3353 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3353
dev_langs:
- C++
helpviewer_keywords:
- C3353
ms.assetid: 5699c04b-d504-46ce-bf71-c200318fed71
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 47a0231a161a2502c26786fceeb1b3634b236eaf
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3353"></a>컴파일러 오류 C3353
'delegate': 대리자는 전역 함수 또는 관리되는 또는 WinRT 형식의 멤버 함수에서만 만들어질 수 있습니다.  
  
 대리자를 사용 하 여 선언 된 [위임](../../windows/delegate-cpp-component-extensions.md) 키워드를 전역 범위에서 선언할 수 있습니다.  
  
 다음 샘플에서는 C3353을 생성합니다.  
  
```  
// C3353.cpp  
// compile with: /clr  
delegate int f;   // C3353  
```
