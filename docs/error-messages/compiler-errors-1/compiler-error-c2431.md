---
title: 컴파일러 오류 C2431 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2431
dev_langs:
- C++
helpviewer_keywords:
- C2431
ms.assetid: 88a5b648-c89f-47d1-a20e-63231ab4f0f7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 94a3f94163e02b953a4739b56a04f92f2499d27f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33197535"
---
# <a name="compiler-error-c2431"></a>컴파일러 오류 C2431
'identifier'에 잘못 된 인덱스 레지스터가 두  
  
 ESP 레지스터를 크기 조정 또는 인덱스와 기본 레지스터로 사용 합니다. Sib 인코딩에 둘은 x86 프로세서 중 하나를 허용 하지 않습니다.  
  
 다음 샘플에서는 C2431 오류가 생성 됩니다.  
  
```  
// C2431.cpp  
// processor: x86  
int main() {  
   _asm mov ax, [ESI + 2*ESP]   // C2431  
   _asm mov ax, [esp + esp]   // C2431  
}  
```