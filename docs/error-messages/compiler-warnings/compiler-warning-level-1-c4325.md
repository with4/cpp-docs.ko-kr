---
title: 컴파일러 경고 (수준 1) C4325 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4325
dev_langs:
- C++
helpviewer_keywords:
- C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 936433987f823ae7d5d22cfd075f188dd5d4b1e4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4325"></a>컴파일러 경고(수준 1) C4325
**표준 섹션에 대 한 특성 '**   
 ***섹션* ' 무시**  
  
 표준 섹션의 특성을 변경할 수 없습니다. 예를 들어:  
  
```  
#pragma section(".sdata", long)  
```  
  
 덮어씁니다.이 `.sdata` 표준 섹션을 사용 하는 **짧은** 데이터 형식에서 **긴** 데이터 형식입니다.  
  
 표준 섹션 바뀌지 않을 해당 특성이 포함  
  
-   .data  
  
-   .sdata  
  
-   .bss  
  
-   .sbss  
  
-   .text  
  
-   .const  
  
-   .sconst  
  
-   .rdata  
  
-   .srdata  
  
 추가 섹션은 나중에 추가할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [section](../../preprocessor/section.md)