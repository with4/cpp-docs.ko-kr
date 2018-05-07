---
title: 컴파일러 오류 C2430 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2430
dev_langs:
- C++
helpviewer_keywords:
- C2430
ms.assetid: 07c20f76-63e1-4d22-b2a9-98b0d45c5cac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 56e1817cf9c5291114af0d94f92e01071d0f7190
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
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