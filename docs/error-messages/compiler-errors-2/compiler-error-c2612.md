---
title: 컴파일러 오류 C2612 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2612
dev_langs:
- C++
helpviewer_keywords:
- C2612
ms.assetid: 6faacfd6-4455-41a2-808e-0f6799f84d6d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e88053cde81e7eea8bc9e9280cf235d5eccc6704
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33226950"
---
# <a name="compiler-error-c2612"></a>컴파일러 오류 C2612
'char' 기본/멤버 이니셜라이저 목록에 잘못 된 후행  
  
 마지막 기본 또는 멤버 이니셜라이저 목록에서 다음에 문자가 표시 합니다.  
  
 다음 샘플에서는 C2612 오류가 생성 됩니다.  
  
```  
// C2612.cpp  
class A {  
public:  
   int i;  
   A( int ia ) : i( ia ) + {};   // C2612  
};  
```