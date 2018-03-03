---
title: "컴파일러 오류 C2431 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2431
dev_langs:
- C++
helpviewer_keywords:
- C2431
ms.assetid: 88a5b648-c89f-47d1-a20e-63231ab4f0f7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4d6c00a8d13739500831e9437c15e3848160183e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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