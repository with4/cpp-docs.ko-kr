---
title: 링커 도구 경고 LNK4197 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4197
dev_langs:
- C++
helpviewer_keywords:
- LNK4197
ms.assetid: 8a976fd7-a74b-4c83-ab66-a9e7d7073c4a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dfef7f0fe2d9cd50fa6a18ad682c3e4d80df99c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300838"
---
# <a name="linker-tools-warning-lnk4197"></a>링커 도구 경고 LNK4197
내보내기 'exportname' 여러 번 지정 했습니다. 첫 번째 사양을 사용 하 여  
  
 내보내기를 여러 번 지정 되었습니다 및 다양 한 방법입니다. 링커는 첫 번째 사양을 사용 하 고 나머지를 무시 합니다.  
  
 C 런타임 라이브러리를 다시 작성 하는 경우이 메시지를 무시할 수 있습니다.  
  
 내보내기가 정확히 같은 방식으로 여러 번 지정 된 경우 링커 경고를 발생 하지 않습니다.  
  
 예를 들어.def 파일의이 경고를 생성.  
  
```  
EXPORTS  
   functioname      NONAME  
   functioname      @10  
```  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면  
  
1.  동일한 내보내기가 지정 된 명령줄에서 둘 다 (내보내기를 통해:) 및.def 파일  
  
2.  동일한 내보내기가 서로 다른 특성을 사용 하 여.def 파일에 두 번 나열 됩니다.