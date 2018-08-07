---
title: -IMPORTS (DUMPBIN) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /imports
dev_langs:
- C++
helpviewer_keywords:
- IMPORTS dumpbin option
- /IMPORTS dumpbin option
- -IMPORTS dumpbin option
ms.assetid: 6a296216-2b1b-40f8-8736-cd4553a22456
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: af3b9a1bbcf1769e87715e46566dee9c53a96747
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373441"
---
# <a name="imports-dumpbin"></a>/IMPORTS(DUMPBIN)
```  
/IMPORTS[:file]  
```  
  
 이 옵션에는 Dll의 목록이 표시 됩니다 (정적으로 링크 둘 다 및 [지연 로드 된](../../build/reference/linker-support-for-delay-loaded-dlls.md))에서 각이 Dll 실행 파일 또는 DLL 및 모든 개별 가져오기 가져온입니다.  
  
 선택적 `file` 사양에는 해당 DLL에 대 한 가져오기 표시 되도록 지정할 수 있습니다. 예를 들어:  
  
```  
dumpbin /IMPORTS:msvcrt.dll  
```  
  
## <a name="remarks"></a>설명  
 이 옵션으로 표시 되는 출력은 비슷합니다는 [/exports](../../build/reference/dash-exports.md) 출력 합니다.  
  
 만 [/HEADERS](../../build/reference/headers.md) DUMPBIN 옵션은으로 생성 된 파일에서 사용 하기 위해 사용할 수는 [/GL](../../build/reference/gl-whole-program-optimization.md) 컴파일러 옵션입니다.  
  
## <a name="see-also"></a>참고 항목  
 [DUMPBIN 옵션](../../build/reference/dumpbin-options.md)