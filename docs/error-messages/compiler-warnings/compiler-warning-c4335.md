---
title: "컴파일러 경고 C4335 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4335
dev_langs:
- C++
helpviewer_keywords:
- C4335
ms.assetid: e66467ad-a10b-4438-8c7c-e8e8d11d39bb
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: ab7406a9c161d47e431cb0af8183d99eac7bfe86
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

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
