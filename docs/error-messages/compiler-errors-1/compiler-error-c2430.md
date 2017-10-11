---
title: "컴파일러 오류 C2430 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2430
dev_langs:
- C++
helpviewer_keywords:
- C2430
ms.assetid: 07c20f76-63e1-4d22-b2a9-98b0d45c5cac
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f5491d998b9c93fc2041c09c19f8b175d319e4d9
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2430"></a>컴파일러 오류 C2430
'identifier'에 둘 이상의 인덱스 등록  
  
 둘 이상의 레지스터 크기가 조정 됩니다. 컴파일러는 배율 조정 된 인덱싱을 지원 하지만 하나의 레지스터 확장할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2430 오류가 발생 합니다.  
  
```  
// C2430.cpp  
// processor: x86  
int main() {  
   _asm mov eax, [ebx*2+ecx*4] // C2430  
}  
```
