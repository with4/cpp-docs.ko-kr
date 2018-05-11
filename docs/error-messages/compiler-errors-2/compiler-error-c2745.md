---
title: 컴파일러 오류 C2745 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2745
dev_langs:
- C++
helpviewer_keywords:
- C2745
ms.assetid: a1c45f13-7667-4678-aa16-265304a449a1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 11f371629c3811821d9c7dce56cc44137534058c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2745"></a>컴파일러 오류 C2745
'token': 식별자에이 토큰을 변환할 수 없습니다  
  
 식별자 반드시 사용할 수 있는 문자로 구성 되어야 합니다.  
  
 다음 샘플에서는 C2745 오류가 생성 됩니다.  
  
```  
// C2745.cpp  
// compile with: /clr  
int main() {  
   int __identifier([));   // C2745  
}  
```