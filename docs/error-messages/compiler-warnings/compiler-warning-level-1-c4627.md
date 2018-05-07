---
title: 컴파일러 경고 (수준 1) C4627 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4627
dev_langs:
- C++
helpviewer_keywords:
- C4627
ms.assetid: 8840f3e6-b496-423a-8635-eb55d5f854a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dcde9e6707465fd95dbcb10e073a852624f0de0a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4627"></a>컴파일러 경고(수준 1) C4627
'\<식별자 >': 미리 컴파일된 헤더 사용을 찾을 때 건너뛰었습니다  
  
 컴파일러는 미리 컴파일된 헤더 사용 되는 위치에 대 한 검색 하는 동안 발생 한 `#include` 지시문에 대 한는  *\<식별자 >* 파일을 포함 합니다. 컴파일러에서 무시는 `#include` 지시문, 경고를 실행 하지만 **C4627** 미리 컴파일된 헤더 포함 되어 있지 않은 경우는  *\<식별자 >* 파일을 포함 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [미리 컴파일된 헤더 파일 만들기](../../build/reference/creating-precompiled-header-files.md)