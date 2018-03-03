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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 04ba07229b1beeb0fdf4362d2b382121ab7606b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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