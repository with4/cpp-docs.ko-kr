---
title: 링커 도구 오류 LNK2011 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2011
dev_langs:
- C++
helpviewer_keywords:
- LNK2011
ms.assetid: 04991ef5-49d5-46c7-8eee-a9d1d3fc541e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f60dce4cb260c670f5ee82aa88b9f106f3f14e2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk2011"></a>링커 도구 오류 LNK2011
미리 컴파일된 개체가 링크 되지 않았습니다. 이미지가 실행 되지 않습니다.  
  
 미리 컴파일된 헤더를 사용 하는 경우 링크에서 링크 해야 미리 컴파일된 헤더를 사용 하 여 만든 개체 파일을 모두 필요 합니다. 다른 소스 파일을 사용 하기 위해 미리 컴파일된 헤더를 생성 하는 데 사용 하는 원본 파일이 있는 경우 미리 컴파일된 헤더와 함께 생성 개체 파일이 이제 포함 되어야 합니다.  
  
 예를 들어 다른 소스 파일 사용 하기 위해 미리 컴파일된 헤더 만들기 STUB.cpp 라는 파일을 컴파일하는 경우 stub.obj 연결 해야 하거나이 오류가 나타납니다. 다음 명령줄에서 줄 하나 COMMON.pch PROG1.cpp 및 PROG2.cpp 줄 2와 3에에서 사용 되는 미리 컴파일된 헤더를 만드는 데 됩니다. STUB.cpp만 포함 하는 파일 `#include` 줄 (동일한 `#include` PROG1.cpp 및 PROG2.cpp 줄)는 미리 컴파일된 헤더를 생성 하는 데에 사용 됩니다. 마지막 줄에서는 LNK2011 방지 하기 위해 STUB.obj에 연결 되어야 합니다.  
  
```  
cl /c /Yccommon.h stub.cpp  
cl /c /Yucommon.h prog1.cpp  
cl /c /Yucommon.h prog2.cpp  
link /out:prog.exe stub.obj prog1.obj prog2.obj  
```