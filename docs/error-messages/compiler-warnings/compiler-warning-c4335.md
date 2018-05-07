---
title: 컴파일러 경고 C4335 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4335
dev_langs:
- C++
helpviewer_keywords:
- C4335
ms.assetid: e66467ad-a10b-4438-8c7c-e8e8d11d39bb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: adb8a7b484ce0946f385c3b2a8669ba1b5ccf0d0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-c4335"></a>컴파일러 경고 C4335
Mac 파일 형식이 발견 되었습니다: 하십시오 소스 파일을 DOS 나 UNIX 형식 변환  
  
 소스 파일의 첫 번째 줄의 줄 종결 문자는 UNIX ('\n') 또는 DOS ('\r\n')이 아니라 Macintosh 스타일 ('\r').  
  
 이 경고는 항상 오류로 서 발생 합니다.  참조 [경고](../../preprocessor/warning.md) 이 경고를 비활성화 하는 방법에 대 한 정보에 대 한 pragma입니다.  또한이 경고가 한 번 compiland 당 합니다. 따라서 여러 개 있는 경우 `#include` 형식 파일을 지정 하는 지시문 C4335 됩니다 수 한 번만 발생 합니다.  
  
 형식에서 파일을 생성 하는 한 가지 방법은 사용 하는 것은 **고급 저장 옵션** (에 **파일** 메뉴) Visual Studio에서.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 c4335 오류가 발생 합니다.  
  
```  
// C4335 expected  
#include "c4335.h"   // assume both include files are in Macintosh format  
#include "c4335_2.h"  
```