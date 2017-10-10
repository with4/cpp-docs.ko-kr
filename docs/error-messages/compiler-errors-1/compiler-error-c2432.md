---
title: "컴파일러 오류 C2432 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2432
dev_langs:
- C++
helpviewer_keywords:
- C2432
ms.assetid: 0e3326e8-cab1-45a5-b48d-61edd33793e8
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d89d894738978359fa0cedb9a9da6c4f9781c135
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2432"></a>컴파일러 오류 C2432
'identifier'에 16 비트 데이터에 대 한 잘못 된 참조  
  
 인덱스 또는 기본 레지스터 16 비트 레지스터 사용 됩니다. 컴파일러는 16 비트 데이터 참조를 지원 하지 않습니다. 32 비트 코드를 컴파일할 때에 인덱스 또는 기본 레지스터로 16 비트 레지스터를 사용할 수 없습니다.  
  
 다음 샘플에서는 C2432 오류가 생성 됩니다.  
  
```  
// C2432.cpp  
// processor: x86  
int main() {  
   _asm mov eax, DWORD PTR [bx]   // C2432  
}  
```
