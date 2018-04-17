---
title: STACKSIZE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- STACKSIZE
dev_langs:
- C++
helpviewer_keywords:
- STACKSIZE .def file statement
ms.assetid: 4d8c79bd-1cb4-4e4d-90f2-b5a7a4d20e7a
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a9c09bea88c4f9452d0fab9371c8b9af8011fd32
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="stacksize"></a>STACKSIZE
스택 크기를 바이트 단위로 설정합니다.  
  
```  
STACKSIZE reserve[,commit]  
```  
  
## <a name="remarks"></a>설명  
 스택 설정 하는 해당 하는 방법은 [스택 할당](../../build/reference/stack-stack-allocations.md) (/stack) 옵션입니다. 에 대 한 자세한 내용은 해당 옵션에 설명서를 참조 하십시오.는 *예약* 및 `commit` 인수입니다.  
  
 이 옵션은 Dll에 대 한 영향을 주지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [모듈 정의 문의 규칙](../../build/reference/rules-for-module-definition-statements.md)