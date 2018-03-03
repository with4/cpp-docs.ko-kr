---
title: "컴파일러 경고 (수준 1) C4325 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4325
dev_langs:
- C++
helpviewer_keywords:
- C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ab31150efc02601d7392470198e162e979ac4917
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4325"></a>컴파일러 경고(수준 1) C4325
**표준 섹션에 대 한 특성 '**   
 ***섹션* ' 무시**  
  
 표준 섹션의 특성을 변경할 수 없습니다. 예:  
  
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