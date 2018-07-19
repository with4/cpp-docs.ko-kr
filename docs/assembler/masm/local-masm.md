---
title: 로컬 (MASM) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- Local
dev_langs:
- C++
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ed9926d23f2e1e8636f31a6f586609ae22d38acd
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
ms.locfileid: "32053573"
---
# <a name="local-masm"></a>LOCAL (MASM)
매크로, 첫 번째 지시문에 **로컬** 매크로의 각 인스턴스에 고유한 레이블을 정의 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      LOCAL localname [[, localname]]...  
LOCAL label [[ [count ] ]] [[:type]] [[, label [[ [count] ]] [[type]]]]...  
```  
  
## <a name="remarks"></a>설명  
 프로시저 정의 내에서 두 번째 지시문에 (**PROC**), **로컬** 절차 중에 존재 하는 스택 기반 변수를 만듭니다. *레이블* 단순 변수 또는 포함 하는 배열 될 수 있습니다 *count* 요소입니다.  
  
## <a name="see-also"></a>참고 항목  
 [지시문 참조](../../assembler/masm/directives-reference.md)