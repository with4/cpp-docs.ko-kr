---
title: "컴파일러 오류 C2055 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2055
dev_langs:
- C++
helpviewer_keywords:
- C2055
ms.assetid: 6cec79cc-6bec-443f-9897-fbf5452718c7
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c447d79179f3575230353b3db70717702b542b68
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2055"></a>컴파일러 오류 C2055
형식 목록이 아니라 정식 매개 변수 목록이 필요합니다.  
  
 함수 정의는 정식 매개 변수 목록 대신 매개 변수 형식 목록이 포함 되어 있습니다. ANSI C에서는 void 또는 줄임표가 아닌 이름을 지정 하는 형식 매개 변수 (`...`).  
  
 다음 샘플에서는 C2055 오류가 생성 됩니다.  
  
```  
// C2055.c  
// compile with: /c  
void func(int, char) {}  // C2055  
void func (int i, char c) {}   // OK  
```
