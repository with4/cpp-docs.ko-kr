---
title: 컴파일러 경고 (수준 1) C4079 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4079
dev_langs:
- C++
helpviewer_keywords:
- C4079
ms.assetid: 549759f0-e168-47e9-8c9a-de93ac843689
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1fc6c58649c16365d1bbeb22dcf0676947d5d8ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4079"></a>컴파일러 경고 (수준 1) C4079
예기치 않은 'token' 토큰입니다.  
  
 예기치 않은 구분 토큰 pragma 인수 목록에서 발생합니다. Pragma의 나머지 부분에서는 무시 되었습니다.  
  
 다음 샘플에서는 C4079 오류가 생성 됩니다.  
  
```  
// C4079.cpp  
// compile with: /W1  
#pragma warning(disable : 4081)  
#pragma pack(c,16)   // C4079  
  
int main() {  
}  
```