---
title: "메모리 덮어쓰기 확인 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: memory, overwrites
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4560fb580d3d1b24feccf84dc07bde7dc38458c2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="checking-for-memory-overwrites"></a>메모리 덮어쓰기 확인
힙 조작 함수에 대 한 호출에서 액세스 위반이 발생 하면 프로그램에 힙 손상 됩니다. 이러한 상황의 일반적인 증상 것입니다.  
  
```  
Access Violation in _searchseg  
```  
  
 [_heapchk](../../c-runtime-library/reference/heapchk.md) 함수는 사용할 수 디버그 및 릴리스 빌드 (Windows NT에만 해당)는 런타임 라이브러리 힙의 무결성을 확인 하는 데 있습니다. 사용할 수 있습니다 `_heapchk` 거의 동일한 방법으로 `AfxCheckMemory` 힙 덮어쓰기 예를 들어 격리 하는 함수:  
  
```  
if(_heapchk()!=_HEAPOK)  
   DebugBreak();  
```  
  
 이 함수가 실패 하는 경우 해야 격리 이때 힙이 손상 되었습니다.  
  
## <a name="see-also"></a>참고 항목  
 [릴리스 빌드 문제 해결](../../build/reference/fixing-release-build-problems.md)