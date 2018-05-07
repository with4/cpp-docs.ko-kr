---
title: 컴파일러 경고 (수준 1) C4326 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4326
dev_langs:
- C++
helpviewer_keywords:
- C4326
ms.assetid: d44d2c4e-9456-42d3-b35b-4ba4b2d42ec7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 838c79d6ba897905dad18788adc5ee682ff2fa2c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4326"></a>컴파일러 경고(수준 1) C4326
'function'의 반환 형식은 'type2' 대신 ' type1' 해야 합니다.  
  
 함수 반환 형식 이외의 ***type1***합니다. 예를 들어,를 사용 하 여 [/Za](../../build/reference/za-ze-disable-language-extensions.md), 주 반환 하지 않았습니다는 `int`합니다.  
  
 다음 샘플에서는 c 4326 오류가 생성 됩니다.  
  
```  
// C4326.cpp  
// compile with: /Za /W1  
char main()  
{   // C4326 try int main  
}  
```