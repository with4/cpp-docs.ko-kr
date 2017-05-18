---
title: "_CRTDBG_MAP_ALLOC | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRTDBG_MAP_ALLOC
- _CRTDBG_MAP_ALLOC
dev_langs:
- C++
helpviewer_keywords:
- _CRTDBG_MAP_ALLOC macro
- memory allocation, in debug builds
- CRTDBG_MAP_ALLOC macro
ms.assetid: 435242b8-caea-4063-b765-4a608200312b
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 709ba57e3cca392d2440c7ad528125dc31070cac
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="crtdbgmapalloc"></a>_CRTDBG_MAP_ALLOC
**_CRTDBG_MAP_ALLOC** 플래그가 응용 프로그램의 디버그 버전에서 정의된 경우 기본 버전의 힙 함수는 해당 디버그 버전에 직접 매핑됩니다. 이 플래그는 매핑을 수행하기 위해 Crtdbg.h에서 사용됩니다. 이 플래그는 [_DEBUG](../c-runtime-library/debug.md) 플래그를 응용 프로그램에서 정의한 경우에만 사용할 수 있습니다.  
  
 힙 함수의 디버그 버전과 기본 버전을 사용하는 방법에 대한 자세한 내용은 [디버그 버전 및 기본 버전 사용](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [제어 플래그](../c-runtime-library/control-flags.md)
