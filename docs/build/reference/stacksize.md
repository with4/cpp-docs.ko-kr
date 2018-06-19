---
title: STACKSIZE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- STACKSIZE
dev_langs:
- C++
helpviewer_keywords:
- STACKSIZE .def file statement
ms.assetid: 4d8c79bd-1cb4-4e4d-90f2-b5a7a4d20e7a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b2093762b3c6f21d319c53a85da5ec5b430a1fd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376249"
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