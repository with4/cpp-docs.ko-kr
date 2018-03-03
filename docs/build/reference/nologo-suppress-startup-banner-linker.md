---
title: "-NOLOGO (시작 배너 표시 안 함) (링커) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.SuppressStartupBanner
- /nologo
dev_langs:
- C++
helpviewer_keywords:
- suppress startup banner linker option
- -NOLOGO linker option
- /NOLOGO linker option
- copyright message
- version numbers, preventing linker display
- banners, suppressing startup
- NOLOGO linker option
ms.assetid: 3b20dddd-eca6-4545-a331-9f70bf720197
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c9cffaea51ad1ba17462292f4feae531361200d8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="nologo-suppress-startup-banner-linker"></a>/NOLOGO(시작 배너 표시 안 함)(링커)
```  
/NOLOGO  
```  
  
## <a name="remarks"></a>설명  
 /NOLOGO 옵션 저작권 메시지와 버전 번호가 표시를 하지 않습니다.  
  
 이 옵션에는 명령 파일의 에코 되지 않습니다. 자세한 내용은 참조 [LINK 명령 파일](../../build/reference/link-command-files.md)합니다.  
  
 기본적으로이 정보는 링커에서 출력 창에 전송 됩니다. 명령줄에서 클래스는 표준 출력으로 전송 되 고 파일로 리디렉션할 수 있습니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  이 옵션은 명령줄에서만 사용 해야 합니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  이 링커 옵션을 프로그래밍 방식으로 변경할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)