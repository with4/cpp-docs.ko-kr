---
title: 링커 도구 경고 LNK4217 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4217
dev_langs:
- C++
helpviewer_keywords:
- LNK4217
ms.assetid: 280dc03e-5933-4e8d-bb8c-891fbe788738
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 625f3a1b8a67f198b1cb4ca37bd1350229ec20db
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4217"></a>링커 도구 경고 LNK4217
' symbol '기호 'function' 함수에서 가져온 로컬 정의 클래스  
  
 [__declspec (dllimport)](../../cpp/dllexport-dllimport.md) 기호가 로컬로 정의 된 경우에 기호에 대해 지정 되었습니다. 제거는 `__declspec` 이 경고를 해결 하려면 한정자입니다.  
  
 `symbol` 이미지 내에 정의 된 기호 이름이입니다. `function` 기호를 가져오는 기능이입니다.  
  
 옵션을 사용 하 여 컴파일하는 경우이 경고가 표시 되지 것입니다 [/clr](../../build/reference/clr-common-language-runtime-compilation.md)합니다.  
  
 LNK4217의 첫 번째 모듈 가져오기 라이브러리를 사용 하 여 두 번째 모듈 컴파일해야 하는 경우 두 개의 모듈을 함께 연결 하려는 경우에 발생할 수 있습니다.  
  
```  
// LNK4217.cpp  
// compile with: /LD  
#include "windows.h"  
__declspec(dllexport) void func(unsigned short*) {}  
```  
  
 그리고  
  
```  
// LNK4217b.cpp  
// compile with: /c  
#include "windows.h"  
__declspec(dllexport) void func(unsigned short*) {}  
```  
  
 이 두 모듈을 연결 하려고 LNK4217 발생 되 면 가져오기 라이브러리를 해결 하려면 첫 번째 샘플의 두 번째 예제를 컴파일합니다.