---
title: 링커 도구 경고 LNK4105 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4105
dev_langs:
- C++
helpviewer_keywords:
- LNK4105
ms.assetid: 6c7bebf4-4ea6-4533-a6ed-e563d43abbd7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ffdd8953e08f38d36bdfc2e68ad6cb8e06fb85b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33304416"
---
# <a name="linker-tools-warning-lnk4105"></a>링커 도구 경고 LNK4105
'option'; 옵션에 지정 된 인수 없음 옵션을 무시합니다.  
  
 이 경고에만 발생 때는 [/LIBPATH](../../build/reference/libpath-additional-libpath.md) 옵션을 설정 합니다. 디렉터리를 지정 하지이 옵션을 링커 옵션 무시 및이 경고 메시지를 생성 합니다.  
  
 기존 환경 라이브러리 설정을 다시 정의 하도록 필요 하지 않은 경우 링커 명령줄에서 /LIBPATH 옵션을 제거 합니다. 라이브러리에 대 한 대체 검색 경로 사용 하려는 경우 /LIBPATH 옵션 다음에 대체 경로 지정 합니다.  
  
## <a name="example"></a>예제  
  
```  
link /libpath:c:\filepath\lib bar.obj  
```  
  
 구문을 사용 하면 링커가에 필요한 라이브러리를 검색할 `c:\filepath\lib` 기본 위치를 검색 하기 전에.