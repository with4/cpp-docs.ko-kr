---
title: . 스택 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .STACK
dev_langs:
- C++
helpviewer_keywords:
- .STACK directive
ms.assetid: 70019463-5d4f-41b6-8464-023a8ac2466f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dab47677da8db2afca73a078b110300a017e7c8d
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="stack"></a>.STACK
와 함께 사용할 경우 [합니다. 모델](../../assembler/masm/dot-model.md), (세그먼트 이름으로 스택) 스택 세그먼트를 정의 합니다. 선택적 `size` 스택 (기본값 1, 024)에 대 한 바이트 수를 지정 합니다. `.STACK` 지시문을 자동으로 스택 문을 닫습니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
.STACK [[size]]  
```  
  
## <a name="see-also"></a>참고 항목  
 [지시문 참조](../../assembler/masm/directives-reference.md)