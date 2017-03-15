---
title: "제어 플래그 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.flags
dev_langs:
- C++
helpviewer_keywords:
- flags, control
- heap allocation, control flags
- debug heap, control flags
ms.assetid: 8dbd24a5-0633-42d1-9771-776db338465f
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 9e8d2030edb3c048ec67ddd5a7b0782d2bbfdd9a
ms.lasthandoff: 02/24/2017

---
# <a name="control-flags"></a>제어 플래그
Microsoft C 런타임 라이브러리의 디버그 버전에서는 힙 할당과 보고 프로세스를 제어하기 위해 다음 플래그를 사용합니다. 자세한 내용은 [CRT 디버깅 기술](/visualstudio/debugger/crt-debugging-techniques)을 참조하세요.  
  
|플래그|설명|  
|----------|-----------------|  
|[_CRTDBG_MAP_ALLOC](../c-runtime-library/crtdbg-map-alloc.md)|기본 힙 함수를 디버그 버전 함수에 매핑합니다.|  
|[_DEBUG](../c-runtime-library/debug.md)|런타임 함수의 디버깅 버전을 사용할 수 있습니다.|  
|[_crtDbgFlag](../c-runtime-library/crtdbgflag.md)|디버그 힙 관리자가 할당을 추적하는 방법을 제어합니다.|  
  
 이러한 플래그는 /D 명령줄 옵션이나 `#define` 명령을 사용하여 정의될 수 있습니다. 플래그가 `#define`을 통해 정의되는 경우 지시문은 루틴 선언의 헤더 파일 include 문보다 앞에 위치해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [전역 변수 및 표준 형식](../c-runtime-library/global-variables-and-standard-types.md)
